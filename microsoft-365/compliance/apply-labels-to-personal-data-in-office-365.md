---
title: 個人データにラベルを適用する
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Office のラベルを一般データ保護規則 (GDPR) 保護計画の一部として使用する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a7bea2abeaec7a858b3cfc693603c46c0f2a416a
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126818"
---
# <a name="apply-labels-to-personal-data"></a><span data-ttu-id="289ca-103">個人データにラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="289ca-103">Apply labels to personal data</span></span>

 <span data-ttu-id="289ca-104">GDPR 保護計画の一環として、分類ラベルを使用している場合は、このトピックを使用します。</span><span class="sxs-lookup"><span data-stu-id="289ca-104">Use this topic if you're using classification labels as part of your GDPR protection plan.</span></span> 

<span data-ttu-id="289ca-105">Microsoft 365 で個人データを保護するためにラベルを使用している場合は、[保持ラベル](retention.md#retention-labels)を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="289ca-105">If you're using labels for protection of personal data in Microsoft 365, Microsoft recommends you start with [retention labels](retention.md#retention-labels).</span></span> <span data-ttu-id="289ca-106">保持ラベルを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="289ca-106">With retention labels, you can:</span></span>
- <span data-ttu-id="289ca-107">アドバンスト データ ガバナンスを使用して、機密情報の種類やその他の基準に基づいてラベルを自動的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="289ca-107">Use Advanced Data Governance to automatically apply labels based on sensitive information types or other criteria.</span></span>
- <span data-ttu-id="289ca-108">データ損失防止機能を備えた保持ラベルを使用して、保護を適用できます。</span><span class="sxs-lookup"><span data-stu-id="289ca-108">Use retention labels with data loss prevention to apply protection.</span></span> 
- <span data-ttu-id="289ca-109">電子情報開示とコンテンツの検索でラベルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="289ca-109">Use labels with eDiscovery and Content Search.</span></span> 

<span data-ttu-id="289ca-110">現在、Cloud App Security は保持ラベルをサポートしていません。ただし、Microsoft 365 の機密情報を Cloud App Security と併用して、別の SaaS アプリにある個人データを監視することはできます。</span><span class="sxs-lookup"><span data-stu-id="289ca-110">Cloud App Security doesn't currently support retention labels, but you can use Microsoft 365 sensitive information types with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>

<span data-ttu-id="289ca-111">[機密ラベル](sensitivity-labels.md)は現在、オンプレミスのファイル、その他のクラウド サービスのファイル、プロバイダーにラベルを適用する場合に推奨されています。</span><span class="sxs-lookup"><span data-stu-id="289ca-111">[Sensitivity labels](sensitivity-labels.md) are currently recommended for applying labels to files on premises and in other cloud services and providers.</span></span> <span data-ttu-id="289ca-112">また、営業秘密ファイルなどのデータ保護用の Azure Information Protection 暗号化を必要とする Microsoft 365 のファイルにも推奨されます。</span><span class="sxs-lookup"><span data-stu-id="289ca-112">These are also recommended for files in Microsoft 365 that require Azure Information Protection encryption for data protection, such as trade secret files.</span></span>

<span data-ttu-id="289ca-113">現時点では、GDPR の対象となるデータを含む Microsoft 365 のファイルに対して Azure Information Protection を使用して暗号化を適用することは、推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="289ca-113">At this time, using Azure Information Protection to apply encryption is not recommended for files in Microsoft 365 with data that is subject to the GDPR.</span></span> <span data-ttu-id="289ca-114">現在、Microsoft 365 サービスでは AIP で暗号化されたファイルへの読み取りはできません。</span><span class="sxs-lookup"><span data-stu-id="289ca-114">Microsoft 365 services currently cannot read into AIP-encrypted files.</span></span> <span data-ttu-id="289ca-115">そのため、サービスでこれらのファイル内の機密データを検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="289ca-115">Therefore, the service can't find sensitive data in these files.</span></span>

<span data-ttu-id="289ca-116">保持ラベルは Exchange Online のメールに適用できます。これらのラベルは Microsoft 365 のデータ損失防止と連動することができます。</span><span class="sxs-lookup"><span data-stu-id="289ca-116">Retention labels can be applied to mail in Exchange Online and these labels work with Microsoft 365 data loss prevention.</span></span> 

![Microsoft 365 のラベルと Azure Information Protection のラベル](../media/Apply-labels-to-personal-data-in-Office-365-image1.png)


<span data-ttu-id="289ca-118">この図について:</span><span class="sxs-lookup"><span data-stu-id="289ca-118">In the illustration:</span></span>

-   <span data-ttu-id="289ca-119">SharePoint Online および OneDrive for Business では、個人データや厳しく規制された営業秘密ファイルに保持ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="289ca-119">Use retention labels for personal data and for highly regulated and trade secret files in SharePoint Online and OneDrive for Business.</span></span>
-   <span data-ttu-id="289ca-120">Microsoft 365 の機密情報の種類を Microsoft 365 内と Cloud App Security で使用して、別の SaaS アプリにある個人データを監視できます。</span><span class="sxs-lookup"><span data-stu-id="289ca-120">Microsoft 365 sensitive information types can be used within Microsoft 365 and with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>
-   <span data-ttu-id="289ca-121">厳しく規制された営業秘密ファイル、Exchange Online 電子メール、他の SaaS サービスのファイル、オンプレミスのデータセンターのファイル、他のクラウド プロバイダーのファイルには、機密ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="289ca-121">Use sensitivity labels for highly regulated and trade secret files, Exchange Online email, files in other SaaS services, files in on-premises datacenters, and files in other cloud providers.</span></span>


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a><span data-ttu-id="289ca-122">情報を保護するために Microsoft 365 全体で保持ラベルと機密情報の種類を使用する</span><span class="sxs-lookup"><span data-stu-id="289ca-122">Use retention labels and sensitive information types across Microsoft 365 for information protection</span></span>

<span data-ttu-id="289ca-123">次の図は、ラベル ポリシー、データ損失防止ポリシー、Cloud App Security ポリシーで保持ラベルと機密情報の種類を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="289ca-123">The following illustration shows how retention labels and sensitive information types can be used in label policies, data loss prevention policies, and with Cloud App Security policies.</span></span>

![Office のラベルと機密情報の種類](../media/Apply-labels-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="289ca-125">次の表では、図での例と同じものを見やすいように記載しています。</span><span class="sxs-lookup"><span data-stu-id="289ca-125">For accessibility, the following table provides the same examples in the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="289ca-126"><strong>分類の要素</strong></span><span class="sxs-lookup"><span data-stu-id="289ca-126"><strong>Classification elements</strong></span></span></th>
<th align="left"><span data-ttu-id="289ca-127"><strong>ラベル ポリシー — 2 つの例</strong></span><span class="sxs-lookup"><span data-stu-id="289ca-127"><strong>Label policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="289ca-128"><strong>データ損失防止ポリシー — 2 つの例</strong></span><span class="sxs-lookup"><span data-stu-id="289ca-128"><strong>Data loss prevention policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="289ca-129"><strong>すべての SaaS アプリの Cloud App Security ポリシー — 1 つの例</strong></span><span class="sxs-lookup"><span data-stu-id="289ca-129"><strong>Cloud App Security policies for all SaaS apps — 1 example</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="289ca-130">保持ラベル。</span><span class="sxs-lookup"><span data-stu-id="289ca-130">Retention labels.</span></span> <span data-ttu-id="289ca-131">例: 個人、公開、顧客のデータ、人事データ、社外秘、非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="289ca-131">Examples: Personal, Public, Customer data, HR data, Confidential, Highly confidential</span></span></td>
<td align="left"><p><span data-ttu-id="289ca-132">Auto apply this label .</span><span class="sxs-lookup"><span data-stu-id="289ca-132">Auto apply this label .</span></span> <span data-ttu-id="289ca-133">.</span><span class="sxs-lookup"><span data-stu-id="289ca-133">.</span></span> <span data-ttu-id="289ca-134">.</span><span class="sxs-lookup"><span data-stu-id="289ca-134">.</span></span></p>
<p><span data-ttu-id="289ca-135">顧客データ</span><span class="sxs-lookup"><span data-stu-id="289ca-135">Customer data</span></span></p>
<p><span data-ttu-id="289ca-136">.</span><span class="sxs-lookup"><span data-stu-id="289ca-136">.</span></span> <span data-ttu-id="289ca-137">.</span><span class="sxs-lookup"><span data-stu-id="289ca-137">.</span></span> <span data-ttu-id="289ca-138">.</span><span class="sxs-lookup"><span data-stu-id="289ca-138">.</span></span> <span data-ttu-id="289ca-139">to documents that match these sensitive information types .</span><span class="sxs-lookup"><span data-stu-id="289ca-139">to documents that match these sensitive information types .</span></span> <span data-ttu-id="289ca-140">.</span><span class="sxs-lookup"><span data-stu-id="289ca-140">.</span></span> <span data-ttu-id="289ca-141">.</span><span class="sxs-lookup"><span data-stu-id="289ca-141">.</span></span></p>
<p><span data-ttu-id="289ca-142">&lt;機密情報の種類の例の一覧&gt;</span><span class="sxs-lookup"><span data-stu-id="289ca-142">&lt;list of example sensitive information types&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="289ca-143">Apply this protection .</span><span class="sxs-lookup"><span data-stu-id="289ca-143">Apply this protection .</span></span> <span data-ttu-id="289ca-144">.</span><span class="sxs-lookup"><span data-stu-id="289ca-144">.</span></span> <span data-ttu-id="289ca-145">.</span><span class="sxs-lookup"><span data-stu-id="289ca-145">.</span></span></p>
<p><span data-ttu-id="289ca-146">&lt;保護の定義&gt;</span><span class="sxs-lookup"><span data-stu-id="289ca-146">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="289ca-147">.</span><span class="sxs-lookup"><span data-stu-id="289ca-147">.</span></span> <span data-ttu-id="289ca-148">.</span><span class="sxs-lookup"><span data-stu-id="289ca-148">.</span></span> <span data-ttu-id="289ca-149">.</span><span class="sxs-lookup"><span data-stu-id="289ca-149">.</span></span> <span data-ttu-id="289ca-150">to documents with this label .</span><span class="sxs-lookup"><span data-stu-id="289ca-150">to documents with this label .</span></span> <span data-ttu-id="289ca-151">.</span><span class="sxs-lookup"><span data-stu-id="289ca-151">.</span></span> <span data-ttu-id="289ca-152">.</span><span class="sxs-lookup"><span data-stu-id="289ca-152">.</span></span></p>
<p><span data-ttu-id="289ca-153">顧客データ</span><span class="sxs-lookup"><span data-stu-id="289ca-153">Customer data</span></span></p></td>
<td align="left"><p><span data-ttu-id="289ca-154">Alert when files with these attributes .</span><span class="sxs-lookup"><span data-stu-id="289ca-154">Alert when files with these attributes .</span></span> <span data-ttu-id="289ca-155">.</span><span class="sxs-lookup"><span data-stu-id="289ca-155">.</span></span> <span data-ttu-id="289ca-156">.</span><span class="sxs-lookup"><span data-stu-id="289ca-156">.</span></span></p>
<p><span data-ttu-id="289ca-157">1 つまたは複数の属性を選択します: 定義済みの PII 属性、Microsoft 365 の機密情報の種類、秘密度ラベル (AIP)、カスタム式</span><span class="sxs-lookup"><span data-stu-id="289ca-157">Choose one or more attributes: predefined PII attribute, Microsoft 365 sensitive information type, sensitivity label (AIP), custom expression</span></span></p>
<p><span data-ttu-id="289ca-158">。</span><span class="sxs-lookup"><span data-stu-id="289ca-158">.</span></span> <span data-ttu-id="289ca-159">。</span><span class="sxs-lookup"><span data-stu-id="289ca-159">.</span></span> <span data-ttu-id="289ca-160">。</span><span class="sxs-lookup"><span data-stu-id="289ca-160">.</span></span> <span data-ttu-id="289ca-161">組織外で共有された際に警告します</span><span class="sxs-lookup"><span data-stu-id="289ca-161">in any sanctioned SaaS app are shared outside the organization</span></span></p><p><span data-ttu-id="289ca-162">注: 現在、保持ラベルは Cloud App Security ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="289ca-162">Note: Retention labels are currently not supported in Cloud App Security.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="289ca-163">Sensitive information types.</span><span class="sxs-lookup"><span data-stu-id="289ca-163">Sensitive information types.</span></span> <span data-ttu-id="289ca-164">Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</span><span class="sxs-lookup"><span data-stu-id="289ca-164">Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</span></span></td>
<td align="left"><p><span data-ttu-id="289ca-165">Publish these labels for users to manually apply .</span><span class="sxs-lookup"><span data-stu-id="289ca-165">Publish these labels for users to manually apply .</span></span> <span data-ttu-id="289ca-166">.</span><span class="sxs-lookup"><span data-stu-id="289ca-166">.</span></span> <span data-ttu-id="289ca-167">.</span><span class="sxs-lookup"><span data-stu-id="289ca-167">.</span></span></p>
<p><span data-ttu-id="289ca-168">&lt;ラベルの選択&gt;</span><span class="sxs-lookup"><span data-stu-id="289ca-168">&lt;select labels&gt;</span></span></p>
<p><span data-ttu-id="289ca-169">.</span><span class="sxs-lookup"><span data-stu-id="289ca-169">.</span></span> <span data-ttu-id="289ca-170">.</span><span class="sxs-lookup"><span data-stu-id="289ca-170">.</span></span> <span data-ttu-id="289ca-171">.</span><span class="sxs-lookup"><span data-stu-id="289ca-171">.</span></span> <span data-ttu-id="289ca-172">to these locations .</span><span class="sxs-lookup"><span data-stu-id="289ca-172">to these locations .</span></span> <span data-ttu-id="289ca-173">.</span><span class="sxs-lookup"><span data-stu-id="289ca-173">.</span></span> <span data-ttu-id="289ca-174">.</span><span class="sxs-lookup"><span data-stu-id="289ca-174">.</span></span></p>
<p><span data-ttu-id="289ca-175">&lt;すべての場所、あるいは特定の場所を選択&gt;</span><span class="sxs-lookup"><span data-stu-id="289ca-175">&lt;all locations or choose specific locations&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="289ca-176">Apply this protection .</span><span class="sxs-lookup"><span data-stu-id="289ca-176">Apply this protection .</span></span> <span data-ttu-id="289ca-177">.</span><span class="sxs-lookup"><span data-stu-id="289ca-177">.</span></span> <span data-ttu-id="289ca-178">.</span><span class="sxs-lookup"><span data-stu-id="289ca-178">.</span></span></p>
<p><span data-ttu-id="289ca-179">&lt;保護の定義&gt;</span><span class="sxs-lookup"><span data-stu-id="289ca-179">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="289ca-180">.</span><span class="sxs-lookup"><span data-stu-id="289ca-180">.</span></span> <span data-ttu-id="289ca-181">.</span><span class="sxs-lookup"><span data-stu-id="289ca-181">.</span></span> <span data-ttu-id="289ca-182">.</span><span class="sxs-lookup"><span data-stu-id="289ca-182">.</span></span> <span data-ttu-id="289ca-183">to documents that match these sensitive information types&gt;</span><span class="sxs-lookup"><span data-stu-id="289ca-183">to documents that match these sensitive information types&gt;</span></span></p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a><span data-ttu-id="289ca-184">自動適用ラベル ポリシーの優先順位付け</span><span class="sxs-lookup"><span data-stu-id="289ca-184">Prioritize auto-apply label policies</span></span>

<span data-ttu-id="289ca-185">For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment.</span><span class="sxs-lookup"><span data-stu-id="289ca-185">For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment.</span></span> <span data-ttu-id="289ca-186">It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.</span><span class="sxs-lookup"><span data-stu-id="289ca-186">It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.</span></span>

<span data-ttu-id="289ca-187">The order that auto-apply policies are created and whether users are also applying these labels affect the result.</span><span class="sxs-lookup"><span data-stu-id="289ca-187">The order that auto-apply policies are created and whether users are also applying these labels affect the result.</span></span> <span data-ttu-id="289ca-188">So, it's important to carefully plan the roll-out. Here's what you need to know.</span><span class="sxs-lookup"><span data-stu-id="289ca-188">So, it's important to carefully plan the roll-out. Here's what you need to know.</span></span>

### <a name="one-label-at-a-time"></a><span data-ttu-id="289ca-189">一度に 1 つのラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="289ca-189">One label at a time</span></span>

<span data-ttu-id="289ca-190">ドキュメントに割り当てることができるラベルの数は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="289ca-190">You can only assign one label to a document.</span></span>

### <a name="older-auto-apply-policies-win"></a><span data-ttu-id="289ca-191">優先されるのは古いポリシー</span><span class="sxs-lookup"><span data-stu-id="289ca-191">Older auto-apply policies win</span></span>

<span data-ttu-id="289ca-192">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned.</span><span class="sxs-lookup"><span data-stu-id="289ca-192">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned.</span></span> <span data-ttu-id="289ca-193">For this reason, it's important to plan the label policies carefully before configuring them.</span><span class="sxs-lookup"><span data-stu-id="289ca-193">For this reason, it's important to plan the label policies carefully before configuring them.</span></span> <span data-ttu-id="289ca-194">If an organization requires a change to the priority of the label policies, they'll need to delete and recreate them.</span><span class="sxs-lookup"><span data-stu-id="289ca-194">If an organization requires a change to the priority of the label policies, they'll need to delete and recreate them.</span></span>

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a><span data-ttu-id="289ca-195">自動適用ラベルよりもユーザーが手動で適用したラベルが優先される</span><span class="sxs-lookup"><span data-stu-id="289ca-195">Manual user-applied labels trump auto-applied labels</span></span>

<span data-ttu-id="289ca-196">Manual user applied labels trump auto-applied labels.</span><span class="sxs-lookup"><span data-stu-id="289ca-196">Manual user applied labels trump auto-applied labels.</span></span> <span data-ttu-id="289ca-197">Auto-apply policies can't replace a label that is already applied by a user.</span><span class="sxs-lookup"><span data-stu-id="289ca-197">Auto-apply policies can't replace a label that is already applied by a user.</span></span> <span data-ttu-id="289ca-198">Users can replace labels that are auto-applied.</span><span class="sxs-lookup"><span data-stu-id="289ca-198">Users can replace labels that are auto-applied.</span></span>

### <a name="auto-assigned-labels-can-be-updated"></a><span data-ttu-id="289ca-199">自動的に割り当てられたラベルは更新可能</span><span class="sxs-lookup"><span data-stu-id="289ca-199">Auto-assigned labels can be updated</span></span>

<span data-ttu-id="289ca-200">自動的に割り当てられたラベルは、新しいラベル ポリシーにより、または既存のポリシーを更新することによって最新の状態にすることができます。</span><span class="sxs-lookup"><span data-stu-id="289ca-200">Auto-assigned labels can be updated by either newer label policies or by updates to existing policies.</span></span>

<span data-ttu-id="289ca-201">ラベルを実装する際に重要な点:</span><span class="sxs-lookup"><span data-stu-id="289ca-201">Be sure your plan for implementing labels includes:</span></span>

- <span data-ttu-id="289ca-202">自動適用ポリシーが作成される順序の優先順位付けを行います。</span><span class="sxs-lookup"><span data-stu-id="289ca-202">Prioritizing the order that auto-apply policies are created.</span></span>

- <span data-ttu-id="289ca-203">Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply.</span><span class="sxs-lookup"><span data-stu-id="289ca-203">Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply.</span></span> <span data-ttu-id="289ca-204">It can take up to seven days for the labels to be applied to all content that matches the conditions.</span><span class="sxs-lookup"><span data-stu-id="289ca-204">It can take up to seven days for the labels to be applied to all content that matches the conditions.</span></span>

### <a name="example-priority-for-creating-the-auto-apply-policies"></a><span data-ttu-id="289ca-205">自動適用ポリシー作成の優先順位の例</span><span class="sxs-lookup"><span data-stu-id="289ca-205">Example priority for creating the auto-apply policies</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="289ca-206"><strong>ラベル</strong></span><span class="sxs-lookup"><span data-stu-id="289ca-206"><strong>Labels</strong></span></span></th>
<th align="left"><span data-ttu-id="289ca-207"><strong>自動適用ポリシーの作成順序の優先順位</strong></span><span class="sxs-lookup"><span data-stu-id="289ca-207"><strong>Priority order to create auto-apply policies</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="289ca-208">人事 — 従業員データ</span><span class="sxs-lookup"><span data-stu-id="289ca-208">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="289ca-209">1</span><span class="sxs-lookup"><span data-stu-id="289ca-209">1</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="289ca-210">顧客データ</span><span class="sxs-lookup"><span data-stu-id="289ca-210">Customer Data</span></span></td>
<td align="left"><span data-ttu-id="289ca-211">2</span><span class="sxs-lookup"><span data-stu-id="289ca-211">2</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="289ca-212">非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="289ca-212">Highly Confidential</span></span></td>
<td align="left"><span data-ttu-id="289ca-213">3</span><span class="sxs-lookup"><span data-stu-id="289ca-213">3</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="289ca-214">人事 — 給与データ</span><span class="sxs-lookup"><span data-stu-id="289ca-214">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="289ca-215">4</span><span class="sxs-lookup"><span data-stu-id="289ca-215">4</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="289ca-216">社外秘</span><span class="sxs-lookup"><span data-stu-id="289ca-216">Confidential</span></span></td>
<td align="left"><span data-ttu-id="289ca-217">5</span><span class="sxs-lookup"><span data-stu-id="289ca-217">5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="289ca-218">公開</span><span class="sxs-lookup"><span data-stu-id="289ca-218">Public</span></span></td>
<td align="left"><span data-ttu-id="289ca-219">6</span><span class="sxs-lookup"><span data-stu-id="289ca-219">6</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="289ca-220">個人</span><span class="sxs-lookup"><span data-stu-id="289ca-220">Personal</span></span></td>
<td align="left"><span data-ttu-id="289ca-221">自動適用ポリシーなし</span><span class="sxs-lookup"><span data-stu-id="289ca-221">No auto-apply policy</span></span></td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a><span data-ttu-id="289ca-222">ラベルおよび自動適用ラベル ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="289ca-222">Create labels and auto-apply label policies</span></span>

<span data-ttu-id="289ca-223">セキュリティ センターまたはコンプライアンス センターで、ラベルおよびポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="289ca-223">Create labels and policies in the security center or the compliance center.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="289ca-224"><strong>手順</strong></span><span class="sxs-lookup"><span data-stu-id="289ca-224"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="289ca-225"><strong>説明</strong></span><span class="sxs-lookup"><span data-stu-id="289ca-225"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="289ca-226">コンプライアンス チームのメンバーにアクセス許可を与えます。</span><span class="sxs-lookup"><span data-stu-id="289ca-226">Give permissions to members of your compliance team.</span></span></p></td>
<td align="left"><p><span data-ttu-id="289ca-227">Members of your compliance team who will create labels need permissions to use the security center and/or the compliance center.</span><span class="sxs-lookup"><span data-stu-id="289ca-227">Members of your compliance team who will create labels need permissions to use the security center and/or the compliance center.</span></span> <span data-ttu-id="289ca-228">Go to Permissions in the security center or the compliance center and modify the members of the Compliance Administrator group.</span><span class="sxs-lookup"><span data-stu-id="289ca-228">Go to Permissions in the security center or the compliance center and modify the members of the Compliance Administrator group.</span></span></p>
<p><span data-ttu-id="289ca-229">「<a href="https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center">ユーザーにセキュリティ センターやコンプライアンス センターへのアクセス権を付与する</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="289ca-229">See <a href="https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center">Give users access to the security center and/or the compliance center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="289ca-230">保持ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="289ca-230">Create retention labels.</span></span></p></td>
<td align="left"><span data-ttu-id="289ca-231">セキュリティ センターまたはコンプライアンス センターの [分類] に移動し、[保持ラベル] を選択して、使用している環境のラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="289ca-231">Go to Classifications in the Security center or the Compliance center, choose Retention labels, and create the labels for your environment.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="289ca-232">ラベルの自動適用ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="289ca-232">Create auto-apply policies for labels.</span></span></p></td>
<td align="left"><span data-ttu-id="289ca-233">Go to Classification in security center or the compliance center, choose Label policies, and create the policies for auto-applying labels.</span><span class="sxs-lookup"><span data-stu-id="289ca-233">Go to Classification in security center or the compliance center, choose Label policies, and create the policies for auto-applying labels.</span></span> <span data-ttu-id="289ca-234">Be sure to create these policies in the prioritized order.</span><span class="sxs-lookup"><span data-stu-id="289ca-234">Be sure to create these policies in the prioritized order.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="289ca-235">次の図は、顧客データ ラベル用の自動適用ラベルを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="289ca-235">The following illustration shows how to create an auto-apply label for the Customer data label.</span></span>

![顧客データのラベルの作成と適用](../media/Apply-labels-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="289ca-237">この図について:</span><span class="sxs-lookup"><span data-stu-id="289ca-237">In the illustration:</span></span>

- <span data-ttu-id="289ca-238">"顧客データ" ラベルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="289ca-238">The "Customer data" label is created.</span></span>

- <span data-ttu-id="289ca-239">GDPR の必要な機密情報の種類 (ベルギーの国民番号、クレジット カード番号、クロアチアの身分証明書番号、フィンランドの国民 ID) が記載されています。</span><span class="sxs-lookup"><span data-stu-id="289ca-239">The desired sensitive information types for GDPR are listed: Belgium National Number, Credit Card Number, Croatia Identity Card Number, Finland National ID.</span></span>

- <span data-ttu-id="289ca-240">自動適用ポリシーを作成すると、ポリシーに追加する機密情報の種類のいずれかを含むファイルに、"顧客データ" ラベルが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="289ca-240">Create an auto-apply policy assigns the label "Customer data" to any file that includes one of the sensitive information types that you add to the policy.</span></span>
