---
title: レコードについての詳細
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
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Microsoft 365 でのレコード管理ソリューションの実装に役立つレコードについて説明します。
ms.openlocfilehash: e64e91aeef307d05f23c47987a84baaf386324df
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685443"
---
# <a name="learn-about-records"></a><span data-ttu-id="23089-103">レコードについての詳細</span><span class="sxs-lookup"><span data-stu-id="23089-103">Learn about records</span></span>

><span data-ttu-id="23089-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="23089-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="23089-105">Microsoft 365 でレコードを管理することで、組織は企業のポリシー、法的および規制上の義務を順守し、リスクや法的責任を軽減することもできます。</span><span class="sxs-lookup"><span data-stu-id="23089-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="23089-106">コンテンツがレコードとしてマークされているときには:</span><span class="sxs-lookup"><span data-stu-id="23089-106">When content is marked as a record:</span></span>

- <span data-ttu-id="23089-107">[アクションが許可またはブロックされている](#compare-restrictions-for-what-actions-are-allowed-or-blocked) という観点から、アイテムに制限がかけられています。</span><span class="sxs-lookup"><span data-stu-id="23089-107">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="23089-108">アイテムに関する追加のアクティビティが記録されます。</span><span class="sxs-lookup"><span data-stu-id="23089-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="23089-109">アイテムが保持期間の終了時に削除された時点で、廃棄の証明を取得します。</span><span class="sxs-lookup"><span data-stu-id="23089-109">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="23089-110">[保持ラベル](retention.md#retention-labels)を使用して、コンテンツをレコードとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="23089-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="23089-111">それらの保持ラベルを発行してユーザーや管理者が手動でコンテンツに適用できるようにするか、レコードとしてマークするコンテンツにそれらのラベルを自動的に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="23089-111">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="23089-112">保持ラベルを使用してコンテンツをレコードとして宣言することで、Microsoft 365 環境全体で単一かつ一貫したレコード管理戦略を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="23089-112">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="23089-113">許可またはブロックするアクションの制限を比較する</span><span class="sxs-lookup"><span data-stu-id="23089-113">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="23089-114">次の表を使用して、標準の保持ラベルを適用した結果、コンテンツに適用される制限事項、およびコンテンツをレコードとしてマークする保持ラベルを特定します。</span><span class="sxs-lookup"><span data-stu-id="23089-114">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="23089-115">標準的な保持ラベルには、コンテンツをレコードとしてマークすることなくデータを保持する構成があります。</span><span class="sxs-lookup"><span data-stu-id="23089-115">A standard retention label has the configuration to retain data without marking content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="23089-116">完全性を期すために、テーブルにはロックされたレコードの列とロック解除されたレコードの列が含まれています。これは、SharePoint と OneDrive には適用できますが、Exchange には適用されません。</span><span class="sxs-lookup"><span data-stu-id="23089-116">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="23089-117">レコードをロックまたはロック解除する機能は、Exchange アイテムでサポートされていない [レコード バージョン管理](record-versioning.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="23089-117">The ability to lock and unlock a record uses [record versioning](record-versioning.md) that isn't supported for Exchange items.</span></span> <span data-ttu-id="23089-118">そのため、レコードとしてマークされているすべての Exchange アイテムについて、[**レコード - ロック済み**] 列に動作がマップされ、[**レコード - ロック解除**] は関連がありません。</span><span class="sxs-lookup"><span data-stu-id="23089-118">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="23089-119">アクション</span><span class="sxs-lookup"><span data-stu-id="23089-119">Action</span></span>| <span data-ttu-id="23089-120">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="23089-120">Retention label</span></span> |<span data-ttu-id="23089-121">レコード - ロック済み</span><span class="sxs-lookup"><span data-stu-id="23089-121">Record - locked</span></span>| <span data-ttu-id="23089-122">レコード - ロック解除</span><span class="sxs-lookup"><span data-stu-id="23089-122">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="23089-123">コンテンツを編集する</span><span class="sxs-lookup"><span data-stu-id="23089-123">Edit contents</span></span>|<span data-ttu-id="23089-124">可</span><span class="sxs-lookup"><span data-stu-id="23089-124">Allowed</span></span> | <span data-ttu-id="23089-125">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="23089-125">**Blocked**</span></span> | <span data-ttu-id="23089-126">可</span><span class="sxs-lookup"><span data-stu-id="23089-126">Allowed</span></span>|
|<span data-ttu-id="23089-127">名前の変更など、プロパティを編集する</span><span class="sxs-lookup"><span data-stu-id="23089-127">Edit properties, including rename</span></span>|<span data-ttu-id="23089-128">可</span><span class="sxs-lookup"><span data-stu-id="23089-128">Allowed</span></span> |<span data-ttu-id="23089-129">可</span><span class="sxs-lookup"><span data-stu-id="23089-129">Allowed</span></span> | <span data-ttu-id="23089-130">可</span><span class="sxs-lookup"><span data-stu-id="23089-130">Allowed</span></span>|
|<span data-ttu-id="23089-131">削除</span><span class="sxs-lookup"><span data-stu-id="23089-131">Delete</span></span>|<span data-ttu-id="23089-132">許可 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="23089-132">Allowed <sup>1</sup></span></span> |<span data-ttu-id="23089-133">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="23089-133">**Blocked**</span></span> | <span data-ttu-id="23089-134">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="23089-134">**Blocked**</span></span>|
|<span data-ttu-id="23089-135">コピー</span><span class="sxs-lookup"><span data-stu-id="23089-135">Copy</span></span>|<span data-ttu-id="23089-136">可</span><span class="sxs-lookup"><span data-stu-id="23089-136">Allowed</span></span> |<span data-ttu-id="23089-137">可</span><span class="sxs-lookup"><span data-stu-id="23089-137">Allowed</span></span> | <span data-ttu-id="23089-138">可</span><span class="sxs-lookup"><span data-stu-id="23089-138">Allowed</span></span>|
|<span data-ttu-id="23089-139">コンテナー内の移動 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23089-139">Move within container <sup>2</sup></span></span>|<span data-ttu-id="23089-140">可</span><span class="sxs-lookup"><span data-stu-id="23089-140">Allowed</span></span> |<span data-ttu-id="23089-141">可</span><span class="sxs-lookup"><span data-stu-id="23089-141">Allowed</span></span> | <span data-ttu-id="23089-142">可</span><span class="sxs-lookup"><span data-stu-id="23089-142">Allowed</span></span>|
|<span data-ttu-id="23089-143">コンテナー間の移動 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="23089-143">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="23089-144">可</span><span class="sxs-lookup"><span data-stu-id="23089-144">Allowed</span></span> |<span data-ttu-id="23089-145">ロック解除されていない場合は許可</span><span class="sxs-lookup"><span data-stu-id="23089-145">Allowed if never unlocked</span></span> | <span data-ttu-id="23089-146">可</span><span class="sxs-lookup"><span data-stu-id="23089-146">Allowed</span></span>|
|<span data-ttu-id="23089-147">開く/読み取り</span><span class="sxs-lookup"><span data-stu-id="23089-147">Open/Read</span></span>|<span data-ttu-id="23089-148">可</span><span class="sxs-lookup"><span data-stu-id="23089-148">Allowed</span></span> |<span data-ttu-id="23089-149">可</span><span class="sxs-lookup"><span data-stu-id="23089-149">Allowed</span></span> | <span data-ttu-id="23089-150">可</span><span class="sxs-lookup"><span data-stu-id="23089-150">Allowed</span></span>|
|<span data-ttu-id="23089-151">ラベルを変更する</span><span class="sxs-lookup"><span data-stu-id="23089-151">Change label</span></span>|<span data-ttu-id="23089-152">可</span><span class="sxs-lookup"><span data-stu-id="23089-152">Allowed</span></span> |<span data-ttu-id="23089-153">許可-コンテナー管理のみ</span><span class="sxs-lookup"><span data-stu-id="23089-153">Allowed - container admin only</span></span> | <span data-ttu-id="23089-154">許可-コンテナー管理のみ</span><span class="sxs-lookup"><span data-stu-id="23089-154">Allowed - container admin only</span></span>|
|<span data-ttu-id="23089-155">ラベルを削除する</span><span class="sxs-lookup"><span data-stu-id="23089-155">Remove label</span></span>|<span data-ttu-id="23089-156">可</span><span class="sxs-lookup"><span data-stu-id="23089-156">Allowed</span></span> |<span data-ttu-id="23089-157">許可-コンテナー管理のみ</span><span class="sxs-lookup"><span data-stu-id="23089-157">Allowed - container admin only</span></span> | <span data-ttu-id="23089-158">許可-コンテナー管理のみ</span><span class="sxs-lookup"><span data-stu-id="23089-158">Allowed - container admin only</span></span>|

<span data-ttu-id="23089-159">脚注:</span><span class="sxs-lookup"><span data-stu-id="23089-159">Footnotes:</span></span>

<span data-ttu-id="23089-160"><sup>1</sup> セキュリティ保護された場所にコピーを保持することによって、OneDrive と Exchange ではサポートされますが、SharePoint ではブロックされます。</span><span class="sxs-lookup"><span data-stu-id="23089-160"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="23089-161">ユーザーが SharePoint のラベル付きドキュメントを削除しようとしたときに表示されるメッセージは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="23089-161">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![SharePoint の「アイテムが削除されませんでした」というメッセージ](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="23089-163"><sup>2</sup> コンテナーには、SharePoint ドキュメント ライブラリと Exchange メールボックスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="23089-163"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>

## <a name="next-steps"></a><span data-ttu-id="23089-164">次の手順</span><span class="sxs-lookup"><span data-stu-id="23089-164">Next steps</span></span>

<span data-ttu-id="23089-165">レコード管理に使用する保持ラベルをまだ作成していない場合は、「[アイテム保持ポリシーと保持ラベルの使用を開始する](get-started-with-retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23089-165">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="23089-166">コンテンツをレコードとしてマークするには、[[保持ラベルを使用してレコードを宣言する](declare-records.md)] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23089-166">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>
