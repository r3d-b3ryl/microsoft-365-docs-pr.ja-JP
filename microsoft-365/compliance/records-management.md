---
title: Microsoft 365 のレコードの管理
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
ms.collection:
- M365-security-compliance
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Microsoft 365 のレコード管理を使用すると、保持スケジュールをファイル計画に適用し、保持、レコード宣言、廃棄を管理することができます。
ms.openlocfilehash: 4f07732e403d711e2fa89bfb7c61c9eadfb2bd0b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926185"
---
# <a name="learn-about-records-management-in-microsoft-365"></a><span data-ttu-id="9aee2-103">Microsoft 365 でのレコード管理について説明します。</span><span class="sxs-lookup"><span data-stu-id="9aee2-103">Learn about records management in Microsoft 365</span></span>

><span data-ttu-id="9aee2-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="9aee2-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="9aee2-105">すべての種類の組織では、企業データ全体にわたって規制、法務およびビジネスに不可欠なレコードを管理するためにレコード管理ソリューションが必要です。</span><span class="sxs-lookup"><span data-stu-id="9aee2-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="9aee2-106">Microsoft 365 のレコード管理は、組織が法的義務を管理できるようにし、規制の遵守を実証する機能を提供します。これにより、ビジネス上、保持する必要がなくなった、価値がなくなった、または不要になったアイテムを定期的に処分することができて効率が向上します。</span><span class="sxs-lookup"><span data-stu-id="9aee2-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="9aee2-107">Microsoft 365 のレコード管理ソリューションをサポートするには、次の機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="9aee2-107">Use the following capabilities to support your records management solution in Microsoft 365:</span></span>

- <span data-ttu-id="9aee2-108">**コンテンツをレコードとして分類する**。</span><span class="sxs-lookup"><span data-stu-id="9aee2-108">**Label content as a record**.</span></span> <span data-ttu-id="9aee2-109">コンテンツを[レコード](#records)としてマークする保持ラベルを作成および構成します。レコードは、ユーザーが適用することも、機密情報、キーワード、またはコンテンツ タイプを識別することにより自動的に適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9aee2-109">Create and configure retention labels to mark content as a [record](#records) that can then be applied by users or automatically applied by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="9aee2-110">**ファイル計画を使用して、保持期間に関する要件を移行して管理します**。</span><span class="sxs-lookup"><span data-stu-id="9aee2-110">**Migrate and manage your retention requirements with file plan**.</span></span> <span data-ttu-id="9aee2-111">[ファイル計画](file-plan-manager.md)を使用して、既存の保持プランを Microsoft 365 に持ち込んだり、新しいプランを構築して管理機能を強化したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9aee2-111">By using a [file plan](file-plan-manager.md), you can bring in an existing retention plan to Microsoft 365, or build a new one for enhanced management capabilities.</span></span>

- <span data-ttu-id="9aee2-112">**保持ラベルを使用して、保持と削除の設定を構成します**。</span><span class="sxs-lookup"><span data-stu-id="9aee2-112">**Configure retention and deletion settings with retention labels**.</span></span> <span data-ttu-id="9aee2-113">保持期間を使用して[保持ラベル](retention.md#retention-labels)を構成したり、最終更新日や作成日などのさまざまな要因に基づきアクションを構成したりします。</span><span class="sxs-lookup"><span data-stu-id="9aee2-113">Configure [retention labels](retention.md#retention-labels) with the retention periods and actions based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="9aee2-114">[イベントベースの保持](event-driven-retention.md)を使って、**イベントが発生したときに、別の保持期間を開始する**。</span><span class="sxs-lookup"><span data-stu-id="9aee2-114">**Start different retention periods when an event occurs** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="9aee2-115">[処理確認](disposition.md#disposition-reviews)、[レコードの削除](disposition.md#disposition-of-records)の証明を使用して **廃棄を確認および検証します**。</span><span class="sxs-lookup"><span data-stu-id="9aee2-115">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="9aee2-116">[[エクスポート] オプション](disposition.md#filter-and-export-the-views)を使用して、**廃棄されたすべてのアイテムに関する情報をエクスポートします**。</span><span class="sxs-lookup"><span data-stu-id="9aee2-116">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="9aee2-117">[適切なアクセス権を取得する](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)ために、組織内のレコード管理機能に **特定のアクセス許可** を設定します。</span><span class="sxs-lookup"><span data-stu-id="9aee2-117">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="9aee2-118">これらの機能を使用すると、組織の保持スケジュールと要件をレコード管理ソリューションに反映させ、保持、レコード宣言、廃棄を管理して、コンテンツのライフサイクル全体をサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="9aee2-118">Using these capabilities, you can incorporate your organization's retention schedules and requirements into a records management solution that manages retention, records declaration, and disposition, to support the full lifecycle of your content.</span></span>

<span data-ttu-id="9aee2-119">オンライン ドキュメントの他にも、レコード管理に関する[ウェビナーの録音](https://aka.ms/MIPC/Video-RecordsManagementWebinar)を聴いたり、[よく寄せられる質問を含む付属のスライド](https://aka.ms/MIPC/Blog-RecordsManagementWebinar)をダウンロードしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9aee2-119">In addition to the online documentation, you might find it useful to listen to the [webinar recording](https://aka.ms/MIPC/Video-RecordsManagementWebinar) for records management, and download the accompanying [deck with FAQs](https://aka.ms/MIPC/Blog-RecordsManagementWebinar).</span></span>

## <a name="records"></a><span data-ttu-id="9aee2-120">レコード</span><span class="sxs-lookup"><span data-stu-id="9aee2-120">Records</span></span>

<span data-ttu-id="9aee2-121">コンテンツがレコードとして宣言されている場合:</span><span class="sxs-lookup"><span data-stu-id="9aee2-121">When content is declared a record:</span></span>

- <span data-ttu-id="9aee2-122">[アクションが許可またはブロックされている](#compare-restrictions-for-what-actions-are-allowed-or-blocked) という観点から、アイテムに制限がかけられています。</span><span class="sxs-lookup"><span data-stu-id="9aee2-122">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="9aee2-123">アイテムに関する追加のアクティビティが記録されます。</span><span class="sxs-lookup"><span data-stu-id="9aee2-123">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="9aee2-124">アイテムが保持期間の終了時に削除された時点で、廃棄の証明を取得します。</span><span class="sxs-lookup"><span data-stu-id="9aee2-124">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="9aee2-125">[保持ラベル](retention.md#retention-labels)を使用して、コンテンツを **レコード** または **規制レコード** としてマークします。</span><span class="sxs-lookup"><span data-stu-id="9aee2-125">You use [retention labels](retention.md#retention-labels) to mark content as a **record**, or a **regulatory record**.</span></span> <span data-ttu-id="9aee2-126">これら 2 つの違いについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="9aee2-126">The difference between these two are explained in the next section.</span></span> <span data-ttu-id="9aee2-127">それらのラベルを発行してユーザーや管理者が手動でコンテンツに適用できるようにするか、レコードまたは規制レコードとしてマークするコンテンツにそれらのラベルを自動的に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="9aee2-127">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record or a regulatory record.</span></span>

<span data-ttu-id="9aee2-128">保持ラベルを使用してレコードとして宣言することで、Microsoft 365 環境全体で単一かつ一貫したレコード管理戦略を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="9aee2-128">By using retention labels to declare records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="9aee2-129">許可またはブロックされているアクションの制限を比較する</span><span class="sxs-lookup"><span data-stu-id="9aee2-129">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="9aee2-130">次の表を使用して、標準の保持ラベルを適用した結果、コンテンツに適用される制限事項、およびコンテンツをレコードまたは規制レコードとしてマークする保持ラベルを特定します。</span><span class="sxs-lookup"><span data-stu-id="9aee2-130">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record or regulatory record.</span></span> 

<span data-ttu-id="9aee2-131">標準の保持ラベルには、保持の設定とアクションが含まれていますが、コンテンツをレコードまたは規制レコードとしてマークしません。</span><span class="sxs-lookup"><span data-stu-id="9aee2-131">A standard retention label has retention settings and actions but doesn't mark content as a record or a regulatory record.</span></span>

>[!NOTE] 
> <span data-ttu-id="9aee2-132">完全性を期すために、テーブルにはロックされたレコードの列とロック解除されたレコードの列が含まれています。これは、SharePoint と OneDrive には適用できますが、Exchange には適用されません。</span><span class="sxs-lookup"><span data-stu-id="9aee2-132">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="9aee2-133">レコードをロックまたはロック解除する機能は、Exchange アイテムでサポートされていない [レコード バージョン管理](record-versioning.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="9aee2-133">The ability to lock and unlock a record uses [record versioning](record-versioning.md) that isn't supported for Exchange items.</span></span> <span data-ttu-id="9aee2-134">そのため、レコードとしてマークされているすべての Exchange アイテムについて、[**レコード - ロック済み**] 列に動作がマップされ、[**レコード - ロック解除**] は関連がありません。</span><span class="sxs-lookup"><span data-stu-id="9aee2-134">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="9aee2-135">アクション</span><span class="sxs-lookup"><span data-stu-id="9aee2-135">Action</span></span>| <span data-ttu-id="9aee2-136">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="9aee2-136">Retention label</span></span> |<span data-ttu-id="9aee2-137">レコード - ロック済み</span><span class="sxs-lookup"><span data-stu-id="9aee2-137">Record - locked</span></span>| <span data-ttu-id="9aee2-138">レコード - ロック解除</span><span class="sxs-lookup"><span data-stu-id="9aee2-138">Record - unlocked</span></span>| <span data-ttu-id="9aee2-139">規制レコード</span><span class="sxs-lookup"><span data-stu-id="9aee2-139">Regulatory record</span></span> |
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9aee2-140">コンテンツを編集する</span><span class="sxs-lookup"><span data-stu-id="9aee2-140">Edit contents</span></span>|<span data-ttu-id="9aee2-141">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-141">Allowed</span></span> | <span data-ttu-id="9aee2-142">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="9aee2-142">**Blocked**</span></span> | <span data-ttu-id="9aee2-143">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-143">Allowed</span></span> | <span data-ttu-id="9aee2-144">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="9aee2-144">**Blocked**</span></span>|
|<span data-ttu-id="9aee2-145">名前の変更など、プロパティを編集する</span><span class="sxs-lookup"><span data-stu-id="9aee2-145">Edit properties, including rename</span></span>|<span data-ttu-id="9aee2-146">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-146">Allowed</span></span> |<span data-ttu-id="9aee2-147">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-147">Allowed</span></span> | <span data-ttu-id="9aee2-148">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-148">Allowed</span></span>| <span data-ttu-id="9aee2-149">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="9aee2-149">**Blocked**</span></span>|
|<span data-ttu-id="9aee2-150">削除</span><span class="sxs-lookup"><span data-stu-id="9aee2-150">Delete</span></span>|<span data-ttu-id="9aee2-151">許可 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9aee2-151">Allowed <sup>1</sup></span></span> |<span data-ttu-id="9aee2-152">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="9aee2-152">**Blocked**</span></span> |<span data-ttu-id="9aee2-153">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="9aee2-153">**Blocked**</span></span>| <span data-ttu-id="9aee2-154">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="9aee2-154">**Blocked**</span></span>|
|<span data-ttu-id="9aee2-155">コピー</span><span class="sxs-lookup"><span data-stu-id="9aee2-155">Copy</span></span>|<span data-ttu-id="9aee2-156">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-156">Allowed</span></span> |<span data-ttu-id="9aee2-157">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-157">Allowed</span></span> | <span data-ttu-id="9aee2-158">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-158">Allowed</span></span>| <span data-ttu-id="9aee2-159">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-159">Allowed</span></span>|
|<span data-ttu-id="9aee2-160">コンテナー内の移動 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9aee2-160">Move within container <sup>2</sup></span></span>|<span data-ttu-id="9aee2-161">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-161">Allowed</span></span> |<span data-ttu-id="9aee2-162">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-162">Allowed</span></span> | <span data-ttu-id="9aee2-163">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-163">Allowed</span></span>| <span data-ttu-id="9aee2-164">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-164">Allowed</span></span>|
|<span data-ttu-id="9aee2-165">コンテナー間の移動 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9aee2-165">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="9aee2-166">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-166">Allowed</span></span> |<span data-ttu-id="9aee2-167">ロック解除されていない場合は許可</span><span class="sxs-lookup"><span data-stu-id="9aee2-167">Allowed if never unlocked</span></span> | <span data-ttu-id="9aee2-168">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="9aee2-168">**Blocked**</span></span> | <span data-ttu-id="9aee2-169">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="9aee2-169">**Blocked**</span></span>|
|<span data-ttu-id="9aee2-170">開く/読み取り</span><span class="sxs-lookup"><span data-stu-id="9aee2-170">Open/Read</span></span>|<span data-ttu-id="9aee2-171">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-171">Allowed</span></span> |<span data-ttu-id="9aee2-172">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-172">Allowed</span></span> | <span data-ttu-id="9aee2-173">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-173">Allowed</span></span>| <span data-ttu-id="9aee2-174">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-174">Allowed</span></span>|
|<span data-ttu-id="9aee2-175">ラベルを変更する</span><span class="sxs-lookup"><span data-stu-id="9aee2-175">Change label</span></span>|<span data-ttu-id="9aee2-176">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-176">Allowed</span></span> |<span data-ttu-id="9aee2-177">許可-コンテナー管理のみ</span><span class="sxs-lookup"><span data-stu-id="9aee2-177">Allowed - container admin only</span></span> | <span data-ttu-id="9aee2-178">許可-コンテナー管理のみ</span><span class="sxs-lookup"><span data-stu-id="9aee2-178">Allowed - container admin only</span></span>| <span data-ttu-id="9aee2-179">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="9aee2-179">**Blocked**</span></span>
|<span data-ttu-id="9aee2-180">ラベルを削除する</span><span class="sxs-lookup"><span data-stu-id="9aee2-180">Remove label</span></span>|<span data-ttu-id="9aee2-181">可</span><span class="sxs-lookup"><span data-stu-id="9aee2-181">Allowed</span></span> |<span data-ttu-id="9aee2-182">許可-コンテナー管理のみ</span><span class="sxs-lookup"><span data-stu-id="9aee2-182">Allowed - container admin only</span></span> | <span data-ttu-id="9aee2-183">許可-コンテナー管理のみ</span><span class="sxs-lookup"><span data-stu-id="9aee2-183">Allowed - container admin only</span></span>| <span data-ttu-id="9aee2-184">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="9aee2-184">**Blocked**</span></span>

<span data-ttu-id="9aee2-185">脚注:</span><span class="sxs-lookup"><span data-stu-id="9aee2-185">Footnotes:</span></span>

<span data-ttu-id="9aee2-186"><sup>1</sup> セキュリティ保護された場所にコピーを保持することによって、OneDrive と Exchange ではサポートされますが、SharePoint ではブロックされます。</span><span class="sxs-lookup"><span data-stu-id="9aee2-186"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="9aee2-187">ドキュメントが添付されているリスト アイテムに保持ラベルを適用する場合、そのドキュメントは保持設定を継承せず、リスト アイテムから削除されます。</span><span class="sxs-lookup"><span data-stu-id="9aee2-187">When you apply a retention label to a list item that has a document attachment, that document doesn't inherit the retention settings and can be deleted from the list item.</span></span> <span data-ttu-id="9aee2-188">対照的に、そのリスト アイテムが保持ラベル付きのレコードとして宣言された場合、ドキュメントの添付ファイルは保持設定を継承し、削除されません。</span><span class="sxs-lookup"><span data-stu-id="9aee2-188">In comparison, if that list item was declared a record with a retention label, the document attachment would inherit the retention settings and couldn't be deleted.</span></span> 

<span data-ttu-id="9aee2-189"><sup>2</sup> コンテナーには、SharePoint ドキュメント ライブラリ、OneDrive アカウントと Exchange メールボックスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9aee2-189"><sup>2</sup> Containers include SharePoint document libraries, OneDrive accounts, and Exchange mailboxes.</span></span>

>[!IMPORTANT] 
> <span data-ttu-id="9aee2-190">規制レコードの最も重要な違いは、コンテンツに適用された後は誰もラベルを削除できず、グローバル管理者でさえもそれを削除できないということです。</span><span class="sxs-lookup"><span data-stu-id="9aee2-190">The most important difference for a regulatory record is that after it is applied to content, nobody, not even a global administrator, can remove the label.</span></span> 
>
> <span data-ttu-id="9aee2-191">規制レコード用に構成された保持ラベルには、次の管理者制限もあります。</span><span class="sxs-lookup"><span data-stu-id="9aee2-191">Retention labels configured for regulatory records also have the following admin restrictions:</span></span>
> - <span data-ttu-id="9aee2-192">ラベルを保存した後に保持期間を短くすることはできず、延長のみが可能です。</span><span class="sxs-lookup"><span data-stu-id="9aee2-192">The retention period can't be made shorter after the label is saved, only extended.</span></span>
> - <span data-ttu-id="9aee2-193">これらのラベルは自動ラベル付けポリシーではサポートされておらず、[保持ラベル ポリシー](create-apply-retention-labels.md)を使用して適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9aee2-193">These labels aren't supported by auto-labeling policies, and must be applied by using [retention label policies](create-apply-retention-labels.md).</span></span> 
>
> <span data-ttu-id="9aee2-194">また、SharePoint でチェックアウトされたドキュメントに規制ラベルを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9aee2-194">In addition, a regulatory label can't be applied to a document that's checked out in SharePoint.</span></span>
> 
> <span data-ttu-id="9aee2-195">これらの制限があり不可逆的なアクションであるため、保持ラベル用にこのオプションを選択する前に、本当に規制レコードを使用する必要があるかどうかをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="9aee2-195">Because of the restrictions and irreversible actions, make sure you really do need to use regulatory records before you select this option for your retention labels.</span></span> <span data-ttu-id="9aee2-196">誤った構成を防止するために、このオプションは既定では使用できなくなっていますが、PowerShell を使用して最初に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9aee2-196">To help prevent accidental configuration, this option is not available by default but must first be enabled by using PowerShell.</span></span> <span data-ttu-id="9aee2-197">手順は、「[保持ラベルを使用してレコードを宣言する](declare-records.md)」に含まれています。</span><span class="sxs-lookup"><span data-stu-id="9aee2-197">Instructions are included in [Declare records by using retention labels](declare-records.md).</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="9aee2-198">構成ガイダンス</span><span class="sxs-lookup"><span data-stu-id="9aee2-198">Configuration guidance</span></span>

<span data-ttu-id="9aee2-199">詳細については、「[レコード管理の概要](get-started-with-records-management.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9aee2-199">See [Get started with records management](get-started-with-records-management.md).</span></span>

<span data-ttu-id="9aee2-200">コンテンツをレコードとしてマークするには、[[保持ラベルを使用してレコードを宣言する](declare-records.md)] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9aee2-200">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>