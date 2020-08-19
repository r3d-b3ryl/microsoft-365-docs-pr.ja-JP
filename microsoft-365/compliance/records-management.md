---
title: レコード管理
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Microsoft 365 のレコード管理を使用すると、保持スケジュールをファイル計画に適用し、保持、レコード宣言、廃棄を管理することができます。
ms.openlocfilehash: c2ff344d22286fcd865aa08344389dad6334d48d
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778325"
---
# <a name="learn-about-records-management"></a><span data-ttu-id="e14de-103">レコード管理の詳細</span><span class="sxs-lookup"><span data-stu-id="e14de-103">Learn about records management</span></span>

><span data-ttu-id="e14de-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="e14de-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="e14de-105">すべての種類の組織では、企業データ全体にわたって規制、法務およびビジネスに不可欠なレコードを管理するためにレコード管理ソリューションが必要です。</span><span class="sxs-lookup"><span data-stu-id="e14de-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="e14de-106">Microsoft 365 のレコード管理は、組織が法的義務を管理できるようにし、規制の遵守を実証する機能を提供します。これにより、ビジネス上、保持する必要がなくなった、価値がなくなった、または不要になったアイテムを定期的に処分することができて効率が向上します。</span><span class="sxs-lookup"><span data-stu-id="e14de-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="e14de-107">Microsoft 365 のレコード管理ソリューションをサポートするには、次の機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="e14de-107">Use the following capabilities to support your records management solution in Microsoft 365:</span></span>

- <span data-ttu-id="e14de-108">**コンテンツをレコードとして分類する**。</span><span class="sxs-lookup"><span data-stu-id="e14de-108">**Label content as a record**.</span></span> <span data-ttu-id="e14de-109">コンテンツを[レコード](#records)としてマークする保持ラベルを作成および構成します。レコードは、ユーザーが適用することも、機密情報、キーワード、またはコンテンツ タイプを識別することにより自動的に適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e14de-109">Create and configure retention labels to mark content as a [record](#records) that can then be applied by users or automatically applied by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="e14de-110">**ファイル計画を使用して、保持期間に関する要件を移行して管理します**。</span><span class="sxs-lookup"><span data-stu-id="e14de-110">**Migrate and manage your retention requirements with file plan**.</span></span> <span data-ttu-id="e14de-111">[ファイル計画](file-plan-manager.md)を使用して、既存の保持プランを Microsoft 365 に持ち込んだり、新しいプランを構築して管理機能を強化したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e14de-111">By using a [file plan](file-plan-manager.md), you can bring in an existing retention plan to Microsoft 365, or build a new one for enhanced management capabilities.</span></span>

- <span data-ttu-id="e14de-112">**保持ラベルを使用して、保持と削除の設定を構成します**。</span><span class="sxs-lookup"><span data-stu-id="e14de-112">**Configure retention and deletion settings with retention labels**.</span></span> <span data-ttu-id="e14de-113">保持期間を使用して[保持ラベル](retention.md#retention-labels)を構成したり、最終更新日や作成日などのさまざまな要因に基づきアクションを構成したりします。</span><span class="sxs-lookup"><span data-stu-id="e14de-113">Configure [retention labels](retention.md#retention-labels) with the retention periods and actions based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="e14de-114">[イベントベースの保持](event-driven-retention.md)を使って、**イベントが発生したときに、別の保持期間を開始する**。</span><span class="sxs-lookup"><span data-stu-id="e14de-114">**Start different retention periods when an event occurs** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="e14de-115">[処理確認](disposition.md#disposition-reviews)、[レコードの削除](disposition.md#disposition-of-records)の証明を使用して**廃棄を確認および検証します**。</span><span class="sxs-lookup"><span data-stu-id="e14de-115">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="e14de-116">[[エクスポート] オプション](disposition.md#filter-and-export-the-views)を使用して、**廃棄されたすべてのアイテムに関する情報をエクスポートします**。</span><span class="sxs-lookup"><span data-stu-id="e14de-116">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="e14de-117">[適切なアクセス権を取得する](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)ために、組織内のレコード管理機能に**特定のアクセス許可**を設定します。</span><span class="sxs-lookup"><span data-stu-id="e14de-117">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="e14de-118">これらの機能を使用すると、組織の保持スケジュールと要件をレコード管理ソリューションに反映させ、保持、レコード宣言、廃棄を管理して、コンテンツのライフサイクル全体をサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="e14de-118">Using these capabilities, you can incorporate your organization's retention schedules and requirements into a records management solution that manages retention, records declaration, and disposition, to support the full lifecycle of your content.</span></span>

<span data-ttu-id="e14de-119">オンライン ドキュメントの他にも、レコード管理に関する[ウェビナーの録音](https://aka.ms/MIPC/Video-RecordsManagementWebinar)を聴いたり、[よく寄せられる質問を含む付属のスライド](https://aka.ms/MIPC/Blog-RecordsManagementWebinar)をダウンロードしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e14de-119">In addition to the online documentation, you might find it useful to listen to the [webinar recording](https://aka.ms/MIPC/Video-RecordsManagementWebinar) for records management, and download the accompanying [deck with FAQs](https://aka.ms/MIPC/Blog-RecordsManagementWebinar).</span></span>

## <a name="records"></a><span data-ttu-id="e14de-120">レコード</span><span class="sxs-lookup"><span data-stu-id="e14de-120">Records</span></span>

<span data-ttu-id="e14de-121">コンテンツがレコードとしてマークされているときには:</span><span class="sxs-lookup"><span data-stu-id="e14de-121">When content is marked as a record:</span></span>

- <span data-ttu-id="e14de-122">[アクションが許可またはブロックされている](#compare-restrictions-for-what-actions-are-allowed-or-blocked) という観点から、アイテムに制限がかけられています。</span><span class="sxs-lookup"><span data-stu-id="e14de-122">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="e14de-123">アイテムに関する追加のアクティビティが記録されます。</span><span class="sxs-lookup"><span data-stu-id="e14de-123">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="e14de-124">アイテムが保持期間の終了時に削除された時点で、廃棄の証明を取得します。</span><span class="sxs-lookup"><span data-stu-id="e14de-124">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="e14de-125">[保持ラベル](retention.md#retention-labels)を使用して、コンテンツをレコードとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="e14de-125">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="e14de-126">それらの保持ラベルを発行してユーザーや管理者が手動でコンテンツに適用できるようにするか、レコードとしてマークするコンテンツにそれらのラベルを自動的に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="e14de-126">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="e14de-127">保持ラベルを使用してコンテンツをレコードとして宣言することで、Microsoft 365 環境全体で単一かつ一貫したレコード管理戦略を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="e14de-127">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="e14de-128">許可またはブロックするアクションの制限を比較する</span><span class="sxs-lookup"><span data-stu-id="e14de-128">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="e14de-129">次の表を使用して、標準の保持ラベルを適用した結果、コンテンツに適用される制限事項、およびコンテンツをレコードとしてマークする保持ラベルを特定します。</span><span class="sxs-lookup"><span data-stu-id="e14de-129">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="e14de-130">標準の保持ラベルには、保持の設定とアクションが含まれていますが、コンテンツをレコードとしてマークしません。</span><span class="sxs-lookup"><span data-stu-id="e14de-130">A standard retention label has retention settings and actions but doesn't mark content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="e14de-131">完全性を期すために、テーブルにはロックされたレコードの列とロック解除されたレコードの列が含まれています。これは、SharePoint と OneDrive には適用できますが、Exchange には適用されません。</span><span class="sxs-lookup"><span data-stu-id="e14de-131">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="e14de-132">レコードをロックまたはロック解除する機能は、Exchange アイテムでサポートされていない [レコード バージョン管理](record-versioning.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e14de-132">The ability to lock and unlock a record uses [record versioning](record-versioning.md) that isn't supported for Exchange items.</span></span> <span data-ttu-id="e14de-133">そのため、レコードとしてマークされているすべての Exchange アイテムについて、[**レコード - ロック済み**] 列に動作がマップされ、[**レコード - ロック解除**] は関連がありません。</span><span class="sxs-lookup"><span data-stu-id="e14de-133">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="e14de-134">アクション</span><span class="sxs-lookup"><span data-stu-id="e14de-134">Action</span></span>| <span data-ttu-id="e14de-135">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="e14de-135">Retention label</span></span> |<span data-ttu-id="e14de-136">レコード - ロック済み</span><span class="sxs-lookup"><span data-stu-id="e14de-136">Record - locked</span></span>| <span data-ttu-id="e14de-137">レコード - ロック解除</span><span class="sxs-lookup"><span data-stu-id="e14de-137">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e14de-138">コンテンツを編集する</span><span class="sxs-lookup"><span data-stu-id="e14de-138">Edit contents</span></span>|<span data-ttu-id="e14de-139">可</span><span class="sxs-lookup"><span data-stu-id="e14de-139">Allowed</span></span> | <span data-ttu-id="e14de-140">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="e14de-140">**Blocked**</span></span> | <span data-ttu-id="e14de-141">可</span><span class="sxs-lookup"><span data-stu-id="e14de-141">Allowed</span></span>|
|<span data-ttu-id="e14de-142">名前の変更など、プロパティを編集する</span><span class="sxs-lookup"><span data-stu-id="e14de-142">Edit properties, including rename</span></span>|<span data-ttu-id="e14de-143">可</span><span class="sxs-lookup"><span data-stu-id="e14de-143">Allowed</span></span> |<span data-ttu-id="e14de-144">可</span><span class="sxs-lookup"><span data-stu-id="e14de-144">Allowed</span></span> | <span data-ttu-id="e14de-145">可</span><span class="sxs-lookup"><span data-stu-id="e14de-145">Allowed</span></span>|
|<span data-ttu-id="e14de-146">削除</span><span class="sxs-lookup"><span data-stu-id="e14de-146">Delete</span></span>|<span data-ttu-id="e14de-147">許可 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e14de-147">Allowed <sup>1</sup></span></span> |<span data-ttu-id="e14de-148">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="e14de-148">**Blocked**</span></span> | <span data-ttu-id="e14de-149">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="e14de-149">**Blocked**</span></span>|
|<span data-ttu-id="e14de-150">コピー</span><span class="sxs-lookup"><span data-stu-id="e14de-150">Copy</span></span>|<span data-ttu-id="e14de-151">可</span><span class="sxs-lookup"><span data-stu-id="e14de-151">Allowed</span></span> |<span data-ttu-id="e14de-152">可</span><span class="sxs-lookup"><span data-stu-id="e14de-152">Allowed</span></span> | <span data-ttu-id="e14de-153">可</span><span class="sxs-lookup"><span data-stu-id="e14de-153">Allowed</span></span>|
|<span data-ttu-id="e14de-154">コンテナー内の移動 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e14de-154">Move within container <sup>2</sup></span></span>|<span data-ttu-id="e14de-155">可</span><span class="sxs-lookup"><span data-stu-id="e14de-155">Allowed</span></span> |<span data-ttu-id="e14de-156">可</span><span class="sxs-lookup"><span data-stu-id="e14de-156">Allowed</span></span> | <span data-ttu-id="e14de-157">可</span><span class="sxs-lookup"><span data-stu-id="e14de-157">Allowed</span></span>|
|<span data-ttu-id="e14de-158">コンテナー間の移動 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e14de-158">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="e14de-159">可</span><span class="sxs-lookup"><span data-stu-id="e14de-159">Allowed</span></span> |<span data-ttu-id="e14de-160">ロック解除されていない場合は許可</span><span class="sxs-lookup"><span data-stu-id="e14de-160">Allowed if never unlocked</span></span> | <span data-ttu-id="e14de-161">可</span><span class="sxs-lookup"><span data-stu-id="e14de-161">Allowed</span></span>|
|<span data-ttu-id="e14de-162">開く/読み取り</span><span class="sxs-lookup"><span data-stu-id="e14de-162">Open/Read</span></span>|<span data-ttu-id="e14de-163">可</span><span class="sxs-lookup"><span data-stu-id="e14de-163">Allowed</span></span> |<span data-ttu-id="e14de-164">可</span><span class="sxs-lookup"><span data-stu-id="e14de-164">Allowed</span></span> | <span data-ttu-id="e14de-165">可</span><span class="sxs-lookup"><span data-stu-id="e14de-165">Allowed</span></span>|
|<span data-ttu-id="e14de-166">ラベルを変更する</span><span class="sxs-lookup"><span data-stu-id="e14de-166">Change label</span></span>|<span data-ttu-id="e14de-167">可</span><span class="sxs-lookup"><span data-stu-id="e14de-167">Allowed</span></span> |<span data-ttu-id="e14de-168">許可-コンテナー管理のみ</span><span class="sxs-lookup"><span data-stu-id="e14de-168">Allowed - container admin only</span></span> | <span data-ttu-id="e14de-169">許可-コンテナー管理のみ</span><span class="sxs-lookup"><span data-stu-id="e14de-169">Allowed - container admin only</span></span>|
|<span data-ttu-id="e14de-170">ラベルを削除する</span><span class="sxs-lookup"><span data-stu-id="e14de-170">Remove label</span></span>|<span data-ttu-id="e14de-171">可</span><span class="sxs-lookup"><span data-stu-id="e14de-171">Allowed</span></span> |<span data-ttu-id="e14de-172">許可-コンテナー管理のみ</span><span class="sxs-lookup"><span data-stu-id="e14de-172">Allowed - container admin only</span></span> | <span data-ttu-id="e14de-173">許可-コンテナー管理のみ</span><span class="sxs-lookup"><span data-stu-id="e14de-173">Allowed - container admin only</span></span>|

<span data-ttu-id="e14de-174">脚注:</span><span class="sxs-lookup"><span data-stu-id="e14de-174">Footnotes:</span></span>

<span data-ttu-id="e14de-175"><sup>1</sup> セキュリティ保護された場所にコピーを保持することによって、OneDrive と Exchange ではサポートされますが、SharePoint ではブロックされます。</span><span class="sxs-lookup"><span data-stu-id="e14de-175"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="e14de-176">ユーザーが SharePoint のラベル付きドキュメントを削除しようとしたときに表示されるメッセージは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e14de-176">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![SharePoint の「アイテムが削除されませんでした」というメッセージ](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="e14de-178"><sup>2</sup> コンテナーには、SharePoint ドキュメント ライブラリと Exchange メールボックスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e14de-178"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e14de-179">次の手順</span><span class="sxs-lookup"><span data-stu-id="e14de-179">Next steps</span></span>

<span data-ttu-id="e14de-180">詳細については、「[レコード管理の概要](get-started-with-records-management.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e14de-180">See [Get started with records management](get-started-with-records-management.md).</span></span>

<span data-ttu-id="e14de-181">コンテンツをレコードとしてマークするには、[[保持ラベルを使用してレコードを宣言する](declare-records.md)] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e14de-181">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>
