---
title: 機密ラベルをコンテンツに自動的に適用する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: 機密ラベルを作成する場合、ドキュメントまたは電子メールにラベルを自動的に割り当てるか、あるいは推奨するラベルを選択するようにユーザーに求めることができます。
ms.openlocfilehash: ee9eef1c8f12d24cdf1c03ee5d7799c63c9acc23
ms.sourcegitcommit: 72e43b9bf85dbf8f5cf2040ea6a4750d6dc867c9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2020
ms.locfileid: "43799980"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="c36b5-103">機密ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="c36b5-103">Apply a sensitivity label to content automatically</span></span>

><span data-ttu-id="c36b5-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="c36b5-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="c36b5-105">機密ラベルを作成する場合、指定した条件に一致したときに、そのラベルをコンテンツに自動的に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-105">When you create a sensitivity label, you can automatically assign that label to content when it matches conditions that you specify.</span></span>

<span data-ttu-id="c36b5-106">機密ラベルを自動的にコンテンツに適用する機能が重要である理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c36b5-106">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="c36b5-107">ユーザーのトレーニングは、一部の分類方法をいつ使用するかについてのみ必要。</span><span class="sxs-lookup"><span data-stu-id="c36b5-107">You don't need to train your users when to use each of your classifications.</span></span>

- <span data-ttu-id="c36b5-108">ユーザーへの依存は、一部のコンテンツを正しく分類するためにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="c36b5-108">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="c36b5-109">ユーザーはポリシーについて把握する必要がなくなり、自分たちの仕事に集中できます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-109">Users no longer need to know about your policies — they can instead focus on their work.</span></span>

<span data-ttu-id="c36b5-110">機密ラベルを自動的に適用するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="c36b5-110">There are two different methods for automatically applying a sensitivity label:</span></span>

- <span data-ttu-id="c36b5-111">**ユーザーがドキュメントを編集したり、メールを作成 (返信または転送) するときのクライアント側のラベル付け**: Office アプリ (Word、Excel、PowerPoint、Outlook) の自動ラベル付け用に構成されたラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-111">**Client-side labeling when users edit documents or compose (also reply or forward) emails**: Use a label that's configured for auto-labeling for Office apps (Word, Excel, PowerPoint, and Outlook).</span></span> 
    
    <span data-ttu-id="c36b5-112">この方法は、ユーザーへのラベルの推奨と、ラベルの自動適用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c36b5-112">This method supports recommending a label to users, as well as automatically applying a label.</span></span> <span data-ttu-id="c36b5-113">ただし、どちらの場合も、ユーザーはラベルを承諾または拒否するかどうかを決定し、コンテンツの正しいラベル付けを行います。</span><span class="sxs-lookup"><span data-stu-id="c36b5-113">But in both cases, the user decides whether to accept or reject the label, to help ensure the correct labeling of content.</span></span> <span data-ttu-id="c36b5-114">このクライアント側のラベル付けでは、ドキュメントを保存する前であってもラベルを適用できるため、ドキュメントの遅延が最小限に抑えられます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-114">This client-side labeling has minimal delay for documents because the label can be applied even before the document is saved.</span></span> <span data-ttu-id="c36b5-115">ただし、すべてのクライアント アプリが自動ラベル付けをサポートしているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c36b5-115">However, not all client apps support auto-labeling.</span></span> <span data-ttu-id="c36b5-116">この機能は、Azure Information Protection 統合ラベル付けクライアント、および [Office の一部のバージョン](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c36b5-116">This capability is supported by the Azure Information Protection unified labeling client, and [some versions of Office](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span> 
    
    <span data-ttu-id="c36b5-117">構成手順については、このページの「[Office アプリの自動ラベル付けを構成する方法](#how-to-configure-auto-labeling-for-office-apps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c36b5-117">For configuration instructions, see [How to configure auto-labeling for Office apps](#how-to-configure-auto-labeling-for-office-apps) on this page.</span></span>

- <span data-ttu-id="c36b5-118">**コンテンツが既に保存されている (SharePoint Online または OneDrive for Business で) またはメールで送信された (Exchange Online によって処理される) サービス側のラベル付け**: 自動ラベル付けポリシーを使用します (現在プレビュー中)。</span><span class="sxs-lookup"><span data-stu-id="c36b5-118">**Service-side labeling when content is already saved (in SharePoint Online or OneDrive for Business) or emailed (processed by Exchange Online)**: Use an auto-labeling policy—currently in preview.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c36b5-119">プレビューのお知らせ、「[Microsoft 365 サービスの機密ラベルを使用した自動分類のパブリック プレビューの発表](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-public-preview-of-auto-classification-with/ba-p/1279961)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c36b5-119">See the preview announcement, [Announcing public preview of auto classification with sensitivity labels in Microsoft 365 services](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-public-preview-of-auto-classification-with/ba-p/1279961).</span></span>
    
    <span data-ttu-id="c36b5-120">この方法は、機密ラベルを使用した自動分類と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-120">This method is referred to as auto classification with sensitivity labels.</span></span> <span data-ttu-id="c36b5-121">また、保存データ (SharePoint および OneDrive のドキュメント) や転送中のデータ (Exchange によって送信または受信されたメール) の自動ラベル付けと呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="c36b5-121">You might also hear it referred to as auto-labeling for data at rest (documents in SharePoint and OneDrive) and data in transit (email that is sent or received by Exchange).</span></span> <span data-ttu-id="c36b5-122">Exchange の場合、保存されているメール (メールボックス) は含まれません。</span><span class="sxs-lookup"><span data-stu-id="c36b5-122">For Exchange, it doesn't include emails at rest (mailboxes).</span></span> 
    
    <span data-ttu-id="c36b5-123">このラベル付けはアプリケーションではなくサービスによって適用されるため、ユーザーが使用しているアプリやバージョンを気にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c36b5-123">Because this labeling is applied by services rather than by applications, you don't need to worry about what apps users have and what version.</span></span> <span data-ttu-id="c36b5-124">その結果、この機能は、組織全体ですぐに使用できるようになります。また、規模に応じたラベル付けに適しています。</span><span class="sxs-lookup"><span data-stu-id="c36b5-124">As a result, this capability is immediately available throughout your organization and suitable for labeling at scale.</span></span> <span data-ttu-id="c36b5-125">自動ラベル付けポリシーでは、ユーザーがラベル付けプロセスを操作しないので、推奨されるラベル付けをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c36b5-125">Auto-labeling policies don't support recommended labeling because the user doesn't interact with the labeling process.</span></span> <span data-ttu-id="c36b5-126">代わりに、管理者は、実際にラベルを適用する前に、コンテンツの正しいラベル付けを行うために、シミュレーション モードでポリシーを実行します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-126">Instead, the administrator runs the policies in simulation mode to help ensure the correct labeling of content before actually applying the label.</span></span>
    
    <span data-ttu-id="c36b5-127">構成手順については、このページの「[SharePoint、OneDrive、Exchange の自動ラベル付けポリシーを構成する方法](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c36b5-127">For configuration instructions, see [How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) on this page.</span></span>
    
    <span data-ttu-id="c36b5-128">SharePoint と OneDrive の自動ラベル付けに固有:</span><span class="sxs-lookup"><span data-stu-id="c36b5-128">Specific to auto-labeling for SharePoint and OneDrive:</span></span>
    - <span data-ttu-id="c36b5-129">テナント内で 1 日あたり最大 25,000 個の自動的にラベル付けされたファイル (Word、PowerPoint、または Excel)</span><span class="sxs-lookup"><span data-stu-id="c36b5-129">Maximum of 25,000 automatically labeled files (Word, PowerPoint, or Excel) in your tenant per day</span></span>
    - <span data-ttu-id="c36b5-130">すべてのポリシー全体で最大 10 のサイト コレクション</span><span class="sxs-lookup"><span data-stu-id="c36b5-130">Maximum of 10 sites collections across all policies</span></span>
    - <span data-ttu-id="c36b5-131">テナント全体で最大 10 のポリシー</span><span class="sxs-lookup"><span data-stu-id="c36b5-131">Maximum of 10 policies across your tenant</span></span>

    <span data-ttu-id="c36b5-132">Exchange の自動ラベル付けに固有:</span><span class="sxs-lookup"><span data-stu-id="c36b5-132">Specific to auto-labeling for Exchange:</span></span>
    - <span data-ttu-id="c36b5-133">手動でのラベル付けや Office アプリを使用した自動ラベル付けとは異なり、Office の添付ファイルも自動ラベル付けポリシーで指定した条件に合わせてスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-133">Unlike manual labeling or auto-labeling with Office apps, Office attachments are also scanned for the conditions you specify in your auto-labeling policy.</span></span> <span data-ttu-id="c36b5-134">一致がある場合、メールにはラベルが付けられますが、添付ファイルにはラベルが付けられません。</span><span class="sxs-lookup"><span data-stu-id="c36b5-134">When there is a match, the email is labeled but not the attachment.</span></span>
    - <span data-ttu-id="c36b5-135">IRM 暗号化を適用する Exchange メール フロー ルールまたはデータ損失防止 (DLP) ポリシーがある場合: これらのルールやポリシーおよび自動ラベル付けポリシーによってコンテンツが識別されると、ラベルが適用されます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-135">If you have Exchange mail flow rules or data loss prevention (DLP) policies that apply IRM encryption: When content is identified by these rules or policies and an auto-labeling policy, the label is applied.</span></span> <span data-ttu-id="c36b5-136">このラベルが暗号化を適用すると、Exchange メール フロー ルールまたは DLP ポリシーの IRM 設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-136">If that label applies encryption, the IRM settings from the Exchange mail flow rules or DLP policies are ignored.</span></span> <span data-ttu-id="c36b5-137">ただし、そのラベルが暗号化を適用しない場合、メール フロー ルールまたは DLP ポリシーの IRM 設定がラベルに加えて適用されます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-137">However, if that label doesn't apply encryption, the IRM settings from the mail flow rules or DLP policies are applied in addition to the label.</span></span>
    - <span data-ttu-id="c36b5-138">ラベルが表示されない IRM 暗号化を使用しているメールは、自動ラベル付けを使用すると一致する場合は、暗号化設定のあるラベルに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-138">Email that has IRM encryption with no label will be replaced by a label with any encryption settings when there is a match by using auto-labeling.</span></span>
    - <span data-ttu-id="c36b5-139">自動ラベル付け条件と一致すると、受信メールにラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-139">Incoming email is labeled when there is a match with your auto-labeling conditions.</span></span> <span data-ttu-id="c36b5-140">ただし、ラベルが暗号化用に構成されている場合、その暗号化は適用されません。</span><span class="sxs-lookup"><span data-stu-id="c36b5-140">However, if the label is configured for encryption, that encryption isn't applied.</span></span>
    

## <a name="compare-auto-labeling-for-office-apps-with-auto-labeling-policies"></a><span data-ttu-id="c36b5-141">Office アプリの自動ラベル付けと自動ラベル付けポリシーを比較する</span><span class="sxs-lookup"><span data-stu-id="c36b5-141">Compare auto-labeling for Office apps with auto-labeling policies</span></span>

<span data-ttu-id="c36b5-142">次の表は、2 つの相補的な自動ラベル付け方法の違いを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-142">Use the following table to help you identify the differences in behavior for the two complementary automatic labeling methods:</span></span>

|<span data-ttu-id="c36b5-143">機能または動作</span><span class="sxs-lookup"><span data-stu-id="c36b5-143">Feature or behavior</span></span>|<span data-ttu-id="c36b5-144">ラベル設定: Office アプリの自動ラベル付け</span><span class="sxs-lookup"><span data-stu-id="c36b5-144">Label setting: Auto-labeling for Office apps</span></span> |<span data-ttu-id="c36b5-145">ポリシー: 自動ラベル付け</span><span class="sxs-lookup"><span data-stu-id="c36b5-145">Policy: Auto-labeling</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c36b5-146">アプリの依存関係</span><span class="sxs-lookup"><span data-stu-id="c36b5-146">App dependency</span></span>|[<span data-ttu-id="c36b5-147">はい</span><span class="sxs-lookup"><span data-stu-id="c36b5-147">Yes</span></span>](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) |<span data-ttu-id="c36b5-148">いいえ</span><span class="sxs-lookup"><span data-stu-id="c36b5-148">No</span></span> |
|<span data-ttu-id="c36b5-149">場所による制限</span><span class="sxs-lookup"><span data-stu-id="c36b5-149">Restrict by location</span></span>|<span data-ttu-id="c36b5-150">いいえ</span><span class="sxs-lookup"><span data-stu-id="c36b5-150">No</span></span> |<span data-ttu-id="c36b5-151">はい</span><span class="sxs-lookup"><span data-stu-id="c36b5-151">Yes</span></span> |
|<span data-ttu-id="c36b5-152">条件: トレーニング可能な分類子</span><span class="sxs-lookup"><span data-stu-id="c36b5-152">Conditions: Trainable classifers</span></span>|<span data-ttu-id="c36b5-153">はい (制限付きプレビュー)</span><span class="sxs-lookup"><span data-stu-id="c36b5-153">Yes (limited preview)</span></span> |<span data-ttu-id="c36b5-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="c36b5-154">No</span></span> |
|<span data-ttu-id="c36b5-155">条件: メールの共有オプションと追加オプション</span><span class="sxs-lookup"><span data-stu-id="c36b5-155">Conditions: Sharing options and additional options for email</span></span>|<span data-ttu-id="c36b5-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="c36b5-156">No</span></span> |<span data-ttu-id="c36b5-157">はい</span><span class="sxs-lookup"><span data-stu-id="c36b5-157">Yes</span></span> |
|<span data-ttu-id="c36b5-158">推奨事項、ポリシーのヒント、ユーザー上書き</span><span class="sxs-lookup"><span data-stu-id="c36b5-158">Recommendations, policy tooltip, and user overrides</span></span>|<span data-ttu-id="c36b5-159">はい</span><span class="sxs-lookup"><span data-stu-id="c36b5-159">Yes</span></span> |<span data-ttu-id="c36b5-160">いいえ</span><span class="sxs-lookup"><span data-stu-id="c36b5-160">No</span></span> |
|<span data-ttu-id="c36b5-161">シミュレーション モード</span><span class="sxs-lookup"><span data-stu-id="c36b5-161">Simulation mode</span></span>|<span data-ttu-id="c36b5-162">いいえ</span><span class="sxs-lookup"><span data-stu-id="c36b5-162">No</span></span> |<span data-ttu-id="c36b5-163">はい</span><span class="sxs-lookup"><span data-stu-id="c36b5-163">Yes</span></span> |
|<span data-ttu-id="c36b5-164">条件についてチェックされた Exchange 添付ファイル</span><span class="sxs-lookup"><span data-stu-id="c36b5-164">Exchange attachments checked for conditions</span></span>|<span data-ttu-id="c36b5-165">いいえ</span><span class="sxs-lookup"><span data-stu-id="c36b5-165">No</span></span> | <span data-ttu-id="c36b5-166">はい</span><span class="sxs-lookup"><span data-stu-id="c36b5-166">Yes</span></span>|
|<span data-ttu-id="c36b5-167">視覚的なマーキングの適用</span><span class="sxs-lookup"><span data-stu-id="c36b5-167">Apply visual markings</span></span> |<span data-ttu-id="c36b5-168">はい</span><span class="sxs-lookup"><span data-stu-id="c36b5-168">Yes</span></span> |<span data-ttu-id="c36b5-169">はい (メール専用)</span><span class="sxs-lookup"><span data-stu-id="c36b5-169">Yes (email only)</span></span> |
|<span data-ttu-id="c36b5-170">ラベルなしで適用された IRM 暗号化の上書き</span><span class="sxs-lookup"><span data-stu-id="c36b5-170">Override IRM encryption applied without a label</span></span>|<span data-ttu-id="c36b5-171">はい (ユーザーがエクスポートの最小使用権を持っている場合)</span><span class="sxs-lookup"><span data-stu-id="c36b5-171">Yes if the user has the minimum usage right of Export</span></span> |<span data-ttu-id="c36b5-172">はい (メール専用)</span><span class="sxs-lookup"><span data-stu-id="c36b5-172">Yes (email only)</span></span> |
|<span data-ttu-id="c36b5-173">受信メールのラベル付け</span><span class="sxs-lookup"><span data-stu-id="c36b5-173">Label incoming email</span></span>|<span data-ttu-id="c36b5-174">いいえ</span><span class="sxs-lookup"><span data-stu-id="c36b5-174">No</span></span> |<span data-ttu-id="c36b5-175">はい (暗号化は適用されません)</span><span class="sxs-lookup"><span data-stu-id="c36b5-175">Yes (encryption not applied)</span></span> |

> [!NOTE]
> <span data-ttu-id="c36b5-176">コンテンツが手動でラベル付けされている場合、そのラベルが自動ラベル付けに置き換えられることはありません。</span><span class="sxs-lookup"><span data-stu-id="c36b5-176">When content has been manually labeled, that label will never be replaced by automatic labeling.</span></span> <span data-ttu-id="c36b5-177">ただし、自動ラベル付けポリシーは、Office アプリの自動ラベル付けを使用して適用された[優先度の低いラベル](sensitivity-labels.md#label-priority-order-matters)を置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-177">However, auto-labeling policies can replace a [lower priority label](sensitivity-labels.md#label-priority-order-matters) that was applied by using auto-labeling for Office apps.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="c36b5-178">複数のラベルに適用するときの複数の条件の評価方法</span><span class="sxs-lookup"><span data-stu-id="c36b5-178">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="c36b5-p108">ラベルは、ポリシー内で指定した位置に従って評価の順序を決められます。先頭に配置したラベルが最下位 (機密性が最も低い) になり、最後に配置したラベルが最上位 (機密性が最も高い) になります。優先度に関する詳細については、「[ラベルの優先度 (順序の問題)](sensitivity-labels.md#label-priority-order-matters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c36b5-p108">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="c36b5-181">自動適用または推奨されるように親ラベルを構成しない</span><span class="sxs-lookup"><span data-stu-id="c36b5-181">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="c36b5-182">親ラベル (サブラベルのあるラベル) はコンテンツに適用できません。</span><span class="sxs-lookup"><span data-stu-id="c36b5-182">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="c36b5-183">Office アプリで親ラベルが自動適用または自動推奨されるように構成されていないこと、自動ラベル ポリシーで親ラベルが選択されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c36b5-183">Make sure that you don't configure a parent label to be auto-applied or recommended in Office apps, and don't select a parent label for an auto-labeling policy.</span></span> <span data-ttu-id="c36b5-184">その場合、親ラベルをコンテンツに適用できなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c36b5-184">If you do, the parent label won't be applied to content.</span></span>

<span data-ttu-id="c36b5-185">自動ラベルでサブラベルも使用するには、必ず親ラベルとサブラベルの両方を発行してください。</span><span class="sxs-lookup"><span data-stu-id="c36b5-185">To use automatic labeling with sublabels, make sure you publish both the parent label and the sublabel.</span></span>

<span data-ttu-id="c36b5-186">親ラベルとサブラベルの詳細については、「[サブラベル (ラベルのグループ化)](sensitivity-labels.md#sublabels-grouping-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c36b5-186">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>

## <a name="how-to-configure-auto-labeling-for-office-apps"></a><span data-ttu-id="c36b5-187">Office アプリの自動ラベル付けを構成する方法</span><span class="sxs-lookup"><span data-stu-id="c36b5-187">How to configure auto-labeling for Office apps</span></span>

<span data-ttu-id="c36b5-188">Windows 用 Office アプリの自動ラベル付けは、Azure Information Protection 統合ラベル付けクライアントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c36b5-188">Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="c36b5-189">Office アプリ組み込みのラベル付けでは、この機能が[一部のアプリでプレビュー](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)されています。</span><span class="sxs-lookup"><span data-stu-id="c36b5-189">For built-in labeling in Office apps, this capability is [in preview for some apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

<span data-ttu-id="c36b5-190">Office アプリの自動ラベル付け設定は、[機密ラベルを作成または編集する](create-sensitivity-labels.md)ときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-190">The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md):</span></span>

![機密ラベルの自動ラベル付けオプション](../media/sensitivity-labels-auto-labeling-options.png)

<span data-ttu-id="c36b5-192">コンテンツに特定の種類の機密情報が含まれている場合、機密ラベルをコンテンツに自動的に適用することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-192">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information.</span></span> <span data-ttu-id="c36b5-193">機密情報の種類または分類子のリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-193">Choose from a list of sensitive info types or classifers:</span></span>

![Office アプリの自動ラベル付けのラベル条件](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> <span data-ttu-id="c36b5-195">現在、**分類子** のオプションは制限付きプレビュー中であり、テナントでこの機能を有効にするには Microsoft にフォームを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c36b5-195">Currently, the option for **Classifers** is in limited preview and requires you to submit a form to Microsoft to enable this capability for your tenant.</span></span> <span data-ttu-id="c36b5-196">詳細については、「[Announcing automatic labeling in Office Apps using built-in classifiers - Limited Preview (組み込みの分類子を使用した Office アプリの自動ラベル付けの発表 - 制限付きプレビュー)](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889)」のブログ投稿を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c36b5-196">For more information, see the blog post [Announcing automatic labeling in Office Apps using built-in classifiers - Limited Preview](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span></span>

<span data-ttu-id="c36b5-197">この機密ラベルが自動的に適用されると、ユーザーの Office アプリに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-197">When this sensitivity label is automatically applied, the user sees a notification in their Office app.</span></span> <span data-ttu-id="c36b5-198">例:</span><span class="sxs-lookup"><span data-stu-id="c36b5-198">For example:</span></span>

![ドキュメントにラベルが自動適用されたという通知](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a><span data-ttu-id="c36b5-200">ラベルの機密情報の種類の構成</span><span class="sxs-lookup"><span data-stu-id="c36b5-200">Configuring sensitive info types for a label</span></span>

<span data-ttu-id="c36b5-201">**機密情報の種類** オプションを選択すると、データ損失防止 (DLP) ポリシーを作成するときと同じ機密情報の種類の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-201">When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="c36b5-202">そのため、たとえば、クレジットカード番号や社会保障番号など、お客様の個人情報 (PII) を含むコンテンツに極秘ラベルを自動的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-202">So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers:</span></span>

![Officeアプリの自動ラベル付け用の機密情報の種類](../media/sensitivity-labels-sensitive-info-types.png)

<span data-ttu-id="c36b5-204">機密情報の種類を選択した後は、インスタンス数または一致精度を変更して条件を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-204">After you select your sensitive information types, you can refine your condition by changing the instance count or match accuracy.</span></span> <span data-ttu-id="c36b5-205">詳細については、「[一致の難易度を設定するためのルールの調整](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c36b5-205">For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="c36b5-206">さらに、条件で検知する必要があるのは、機密情報の種類のすべてか、またはそのうちの 1 つだけかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-206">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="c36b5-207">また、条件をより柔軟または複雑にするには、グループを追加し、グループ間で論理演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-207">And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups.</span></span> <span data-ttu-id="c36b5-208">詳細については、「[グループ化および論理演算子](data-loss-prevention-policies.md#grouping-and-logical-operators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c36b5-208">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

![インスタンス数と一致精度のオプション](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifers-for-a-label"></a><span data-ttu-id="c36b5-210">ラベルの分類子の構成</span><span class="sxs-lookup"><span data-stu-id="c36b5-210">Configuring classifers for a label</span></span>

<span data-ttu-id="c36b5-211">**分類子** オプションを選択する場合、1 つ以上の組み込み分類子を選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-211">When you select the **Classifers** option, select one or more of the built-in classifiers:</span></span>

![分類子と機密ラベルのオプション](../media/sensitivity-labels-classifers.png)

<span data-ttu-id="c36b5-213">それらの分類子の詳細については、「[トレーニング可能な分類子 (プレビュー) の概要](classifier-getting-started-with.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c36b5-213">For more information about these classifers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="c36b5-214">プレビュー期間中は、次のアプリが機密ラベルの分類子をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c36b5-214">During the preview period, the following apps support classifers for sensitivity labels:</span></span>

- <span data-ttu-id="c36b5-215">[Office Insider](https://office.com/insider) の Windows 用 Microsoft 365 Apps for enterprise デスクトップ アプリ:</span><span class="sxs-lookup"><span data-stu-id="c36b5-215">Microsoft365 Apps for enterprise desktop apps for Windows, from [Office Insider](https://office.com/insider):</span></span>
    - <span data-ttu-id="c36b5-216">Word</span><span class="sxs-lookup"><span data-stu-id="c36b5-216">Word</span></span>
    - <span data-ttu-id="c36b5-217">Excel</span><span class="sxs-lookup"><span data-stu-id="c36b5-217">Excel</span></span>
    - <span data-ttu-id="c36b5-218">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c36b5-218">PowerPoint</span></span>

- <span data-ttu-id="c36b5-219">[SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にする機能 (パブリック プレビュー)](sensitivity-labels-sharepoint-onedrive-files.md) が有効になっている場合の Web アプリ用の Office:</span><span class="sxs-lookup"><span data-stu-id="c36b5-219">Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    - <span data-ttu-id="c36b5-220">Word</span><span class="sxs-lookup"><span data-stu-id="c36b5-220">Word</span></span>
    - <span data-ttu-id="c36b5-221">Excel</span><span class="sxs-lookup"><span data-stu-id="c36b5-221">Excel</span></span>
    - <span data-ttu-id="c36b5-222">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c36b5-222">PowerPoint</span></span>
    - <span data-ttu-id="c36b5-223">Outlook</span><span class="sxs-lookup"><span data-stu-id="c36b5-223">Outlook</span></span>

### <a name="recommend-that-the-user-applies-a-sensitivity-label"></a><span data-ttu-id="c36b5-224">ユーザーが秘密度ラベルを適用することを推奨</span><span class="sxs-lookup"><span data-stu-id="c36b5-224">Recommend that the user applies a sensitivity label</span></span>

<span data-ttu-id="c36b5-225">状況に応じて、ユーザーがラベルを適用することを推奨できます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-225">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="c36b5-226">このオプションでは、分類および関連する保護を受け入れるか、またはラベルがそのコンテンツに適していない場合、推奨事項を無視するかをユーザーが選択できます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-226">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.</span></span>

![機密ラベルをユーザーに推奨するためのオプション](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="c36b5-p118">ラベルを推奨される操作として適用するように条件を構成したときの、Azure Information Protection の統合ラベル付けクライアントからのプロンプトの例を、カスタム ポリシー ヒントと共に示します。ポリシー ヒントに表示するテキストを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-p118">Here's an example of a prompt from the Azure Information Protection unified labeling client when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.</span></span>

![推奨ラベルを適用するためのプロンプト](../media/Sensitivity-label-Prompt-for-required-label.png)

### <a name="when-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="c36b5-231">自動ラベルまたは推奨ラベルが適用されている場合</span><span class="sxs-lookup"><span data-stu-id="c36b5-231">When automatic or recommended labels are applied</span></span>

<span data-ttu-id="c36b5-232">Office アプリでの自動ラベル付けと推奨ラベル付けの実装は、Office に組み込まれているラベル付けを使用しているか、または Azure Information Protection の統合ラベル付けクライアントを使用しているかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c36b5-232">The implementation of automatic and recommended labeling in Office apps depend on whether you're using labeling that's built into Office, or the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="c36b5-233">ただし、どちらの場合も次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c36b5-233">In both cases, however:</span></span>

- <span data-ttu-id="c36b5-234">以前に手動でラベルが付けられているか、以前に上位の機密度で自動的にラベルが付けられているドキュメントと電子メールには自動ラベル付けを使用できません。</span><span class="sxs-lookup"><span data-stu-id="c36b5-234">You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity.</span></span> <span data-ttu-id="c36b5-235">ドキュメントや電子メールに適用できる機密ラベルは (1 つの保持ラベルに加えて) 1 つだけであることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="c36b5-235">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="c36b5-236">以前に上位の秘密度でラベルが付けられているドキュメントまたはメールには推奨ラベル付けを使用できません。</span><span class="sxs-lookup"><span data-stu-id="c36b5-236">You can't use recommended labeling for documents or emails that were previously labeled with a higher sensitivity.</span></span> <span data-ttu-id="c36b5-237">コンテンツに既に上位の秘密度でラベルが付けられている場合、推奨事項とポリシー ヒントに関するプロンプトは、ユーザーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="c36b5-237">When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.</span></span>

<span data-ttu-id="c36b5-238">組み込みのラベル付けに関してのみ以下の点が当てはまります。</span><span class="sxs-lookup"><span data-stu-id="c36b5-238">Specific to built-in labeling:</span></span>

- <span data-ttu-id="c36b5-239">必ずしもすべての Office アプリで自動 (および推奨) ラベル付けがサポートされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c36b5-239">Not all Office apps support automatic (and recommended) labeling.</span></span> <span data-ttu-id="c36b5-240">詳しくは、「[アプリでの秘密度ラベル機能のサポート](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c36b5-240">For more information, see [Support for sensitivity label capabilities in apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

- <span data-ttu-id="c36b5-241">Word のデスクトップ バージョンにおける推奨ラベルでは、推奨をトリガーした機密コンテンツにフラグが付けられるので、ユーザーが確認して、推奨されている秘密度ラベルを適用しないで機密コンテンツを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-241">For recommended labels in the desktop versions of Word, the sensitive content that triggered the recommendation is flagged so that users can review and remove the sensitive content instead of applying the recommended sensitivity label.</span></span>

- <span data-ttu-id="c36b5-242">こうしたラベルが Office アプリで適用される方法、スクリーンショット例、機密情報の検出方法について詳しくは、「[Office のファイルとメールに秘密度ラベルを自動的に適用、または推奨する](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c36b5-242">For details about how these labels are applied in Office apps, example screenshots, and how sensitive information is detected, see [Automatically apply or recommend sensitivity labels to your files and emails in Office](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1).</span></span>

<span data-ttu-id="c36b5-243">Azure Information Protection 統合ラベル付けクライアントに関してのみ以下の点が当てはまります。</span><span class="sxs-lookup"><span data-stu-id="c36b5-243">Specific to the Azure Information Protection unified labeling client:</span></span>

-  <span data-ttu-id="c36b5-244">自動ラベル付けと推奨ラベル付けは、Word、Excel、PowerPoint でドキュメントが保存されるときと、Outlook でメールが送信されるときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-244">Automatic and recommended labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span>

- <span data-ttu-id="c36b5-245">Outlook で推奨ラベル付けをサポートするには、最初に[詳細なポリシー設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook)を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c36b5-245">For Outlook to support recommended labeling, you must first configure an [advanced policy setting](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook).</span></span>

- <span data-ttu-id="c36b5-246">ドキュメントやメール内の本文、およびヘッダーとフッターに含まれる機密情報が検出されますが、件名やメールの添付ファイルのものは検知されません。</span><span class="sxs-lookup"><span data-stu-id="c36b5-246">Sensitive information can be detected in the body text in documents and emails, and to headers and footers — but not in the subject line or attachments of email.</span></span>

## <a name="how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange"></a><span data-ttu-id="c36b5-247">SharePoint、OneDrive、Exchange の自動ラベル付けポリシーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="c36b5-247">How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange</span></span>
> [!NOTE]
> <span data-ttu-id="c36b5-248">自動ラベル付けポリシーは、パブリック プレビューでテナントに段階的に展開されており、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c36b5-248">Auto-labeling policies are gradually rolling out to tenants in public preview and subject to change.</span></span>

### <a name="prerequisites-for-auto-labeling-policies"></a><span data-ttu-id="c36b5-249">自動ラベル付けポリシーの前提条件</span><span class="sxs-lookup"><span data-stu-id="c36b5-249">Prerequisites for auto-labeling policies</span></span>

- <span data-ttu-id="c36b5-250">シミュレーション モードでは、Microsoft 365 の監査を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c36b5-250">Auditing for Microsoft 365 must be turned on for simulation mode.</span></span> <span data-ttu-id="c36b5-251">監査を有効にする必要がある場合、または監査が既に有効になっているかどうかが不明の場合は、「[監査ログの検索を有効または無効にする](turn-audit-log-search-on-or-off.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c36b5-251">If you need to turn on auditing or you're not sure whether auditing is already on, see [Turn audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="c36b5-252">SharePoint と OneDrive でファイルに自動でラベルを付けるには:</span><span class="sxs-lookup"><span data-stu-id="c36b5-252">To auto-label files in SharePoint and OneDrive:</span></span>
    - <span data-ttu-id="c36b5-253">[SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする (パブリック プレビュー)](sensitivity-labels-sharepoint-onedrive-files.md) を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="c36b5-253">You have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>
    - <span data-ttu-id="c36b5-254">自動ラベル付けポリシーの実行時に、別のプロセスまたはユーザーがファイルを開いておくことはできません。</span><span class="sxs-lookup"><span data-stu-id="c36b5-254">At the time the auto-labeling policy runs, the file mustn't be open by another process or user.</span></span>

- <span data-ttu-id="c36b5-255">組み込みの機密度の種類ではなく、[カスタムの機密情報の種類](custom-sensitive-info-types.md)を使用する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c36b5-255">If you plan to use [custom sensitive information types](custom-sensitive-info-types.md) rather than the built-in sensitivity types:</span></span> 
    - <span data-ttu-id="c36b5-256">カスタムの機密情報の種類は、カスタムの機密情報の種類が保存された後に作成されたコンテンツに対して評価されます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-256">Custom sensitivity information types are evaluated for content that is created after the custom sensitivity information types are saved.</span></span> 
    - <span data-ttu-id="c36b5-257">新しいカスタムの機密情報の種類をテストするには、自動ラベル付けポリシーを作成する前に作成してから、テスト用のサンプル データを使用して新しいドキュメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-257">To test new custom sensitive information types, create them before you create your auto-labeling policy, and then create new documents with sample data for testing.</span></span>

- <span data-ttu-id="c36b5-258">自動ラベル付けポリシー用に選択できる、[作成および公開された](create-sensitivity-labels.md) (少なくとも 1 人のユーザーに対して) 1 つ以上の秘密度ラベル。</span><span class="sxs-lookup"><span data-stu-id="c36b5-258">One or more sensitivity labels [created and published](create-sensitivity-labels.md) (to at least one user) that you can select for your auto-labeling policies.</span></span> <span data-ttu-id="c36b5-259">これらのラベルの場合:</span><span class="sxs-lookup"><span data-stu-id="c36b5-259">For these labels:</span></span>
    - <span data-ttu-id="c36b5-260">概要で説明したように、ラベル設定は自動ラベル付けポリシーを補完するため、Office アプリのラベル設定の自動ラベル付けがオンかオフかは関係ありません。</span><span class="sxs-lookup"><span data-stu-id="c36b5-260">It doesn't matter if the auto-labeling in Office apps label setting is turned on or off, because that label setting supplements auto-labeling policies, as explained in the introduction.</span></span> 
    - <span data-ttu-id="c36b5-261">自動ラベル付けに使用するラベルが視覚的なマーキング (ヘッダー、フッター、透かし) を使用するように構成されている場合、これらはドキュメントに適用されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c36b5-261">If the labels you want to use for auto-labeling are configured to use visual markings (headers, footers, watermarks), note that these are not applied to documents.</span></span>
    - <span data-ttu-id="c36b5-262">ラベルに暗号化を適用する場合は、**[今すぐアクセス許可を適用する]** の設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c36b5-262">If the labels apply encryption, they must be configured for the **Apply permissions now** setting.</span></span>

### <a name="learn-about-simulation-mode"></a><span data-ttu-id="c36b5-263">シミュレーション モードの詳細</span><span class="sxs-lookup"><span data-stu-id="c36b5-263">Learn about simulation mode</span></span>

<span data-ttu-id="c36b5-264">シミュレーション モードは、自動ラベル付けポリシーに固有であり、ワークフローに組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="c36b5-264">Simulation mode is unique to auto-labeling policies and woven into the workflow.</span></span> <span data-ttu-id="c36b5-265">ポリシーによって少なくとも 1 つのシミュレーションが実行されるまで、ドキュメントとメールに自動的にラベルを付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="c36b5-265">You can't automatically label documents and emails until your policy has run at least one simulation.</span></span>

<span data-ttu-id="c36b5-266">自動ラベル付けポリシーのワークフロー:</span><span class="sxs-lookup"><span data-stu-id="c36b5-266">Workflow for an auto-labeling policy:</span></span>

1. <span data-ttu-id="c36b5-267">自動ラベル付けポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="c36b5-267">Create and configure an auto-labeling policy</span></span>

2. <span data-ttu-id="c36b5-268">シミュレーション モードでポリシーを実行し、少なくとも 24 時間待機する</span><span class="sxs-lookup"><span data-stu-id="c36b5-268">Run the policy in simulation mode and wait at least 24 hours</span></span>

3. <span data-ttu-id="c36b5-269">結果を確認し、必要に応じてポリシーを調整し、シミュレーション モードを再実行して、少なくとも 24 時間待機する</span><span class="sxs-lookup"><span data-stu-id="c36b5-269">Review the results, and if necessary, refine your policy, rerun simulation mode and wait at least 24 hours</span></span>

4. <span data-ttu-id="c36b5-270">必要に応じて、手順 3 を繰り返します</span><span class="sxs-lookup"><span data-stu-id="c36b5-270">Repeat step 3 as needed</span></span>

5. <span data-ttu-id="c36b5-271">本稼働に展開</span><span class="sxs-lookup"><span data-stu-id="c36b5-271">Deploy in production</span></span>

<span data-ttu-id="c36b5-272">シミュレーションされた展開は、PowerShell の WhatIf パラメーターのように動作します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-272">The simulated deployment runs like the WhatIf parameter for PowerShell.</span></span> <span data-ttu-id="c36b5-273">定義したルールを使用して、自動ラベル付けポリシーが選択したラベルを適用したかのようにレポートされた結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-273">You see results reported as if the auto-labeling policy had applied your selected label, using the rules that you defined.</span></span> <span data-ttu-id="c36b5-274">その後、必要に応じてルールの精度を高め、シミュレーションを再実行できます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-274">You can then refine your rules for accuracy if needed, and rerun the simulation.</span></span> <span data-ttu-id="c36b5-275">ただし、Exchange の自動ラベル付けは、メールボックスに保存されたメールではなく、送受信されるメールに適用されるため、完全に同じメール メッセージを送受信することができなければ、シミュレーションのメールの結果に一貫性があるとは期待できません。</span><span class="sxs-lookup"><span data-stu-id="c36b5-275">However, because auto-labeling for Exchange applies to emails that are sent and received, rather than emails stored in mailboxes, don't expect results for email in a simulation to be consistent unless you're able to send and receive the exact same email messages.</span></span>

<span data-ttu-id="c36b5-276">シミュレーション モードでは、展開前に自動ラベル付けポリシーの範囲を徐々に広げることもできます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-276">Simulation mode also lets you gradually increase the scope of your auto-labeling policy before deployment.</span></span> <span data-ttu-id="c36b5-277">たとえば、1 つのドキュメント ライブラリを持った SharePoint サイトなどの 1 つの場所から始めることができます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-277">For example, you might start with a single location, such as a SharePoint site, with a single document library.</span></span> <span data-ttu-id="c36b5-278">次に、反復的な変更を加えて、範囲を複数のサイトに拡大し、次に OneDrive などの別の場所に拡大します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-278">Then, with iterative changes, increase the scope to multiple sites, and then to another location, such as OneDrive.</span></span>

<span data-ttu-id="c36b5-279">最後に、シミュレーション モードを使用して、自動ラベル付けポリシーの実行に必要な時間の概算を提供し、シミュレーション モードを使用せずに実行するタイミングを計画してスケジュールすることができます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-279">Finally, you can use simulation mode to provide an approximation of the time needed to run your auto-labeling policy, to help you plan and schedule when to run it without simulation mode.</span></span>

### <a name="creating-an-auto-labeling-policy"></a><span data-ttu-id="c36b5-280">自動ラベル付けポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="c36b5-280">Creating an auto-labeling policy</span></span>

1. <span data-ttu-id="c36b5-281">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、機密ラベルに移動します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-281">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="c36b5-282">[**ソリューション**]  >  [**Information Protection**]</span><span class="sxs-lookup"><span data-stu-id="c36b5-282">**Solutions** > **Information protection**</span></span>
    
    <span data-ttu-id="c36b5-283">このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-283">If you don't immediately see this option, first select **Show all**.</span></span>

2. <span data-ttu-id="c36b5-284">[**自動ラベル付 (プレビュー)**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-284">Select the **Auto-labeling (preview)** tab:</span></span>
    
    ![自動ラベル付け (プレビュー) タブ](../media/auto-labeling-tab.png)
    
    <span data-ttu-id="c36b5-286">この新しいタブは現在、テナントにロールアウト中です。</span><span class="sxs-lookup"><span data-stu-id="c36b5-286">This new tab is still rolling out to tenants.</span></span> <span data-ttu-id="c36b5-287">表示されない場合は、数日後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="c36b5-287">If you don't see it, try again in a few days.</span></span>

3. <span data-ttu-id="c36b5-288">[**+ ポリシーの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-288">Select **+ Create policy**.</span></span>

4. <span data-ttu-id="c36b5-289">[**このラベルを適用する情報を選択する**] ページの場合: [**財務**] または [**プライバシー**] などのテンプレートのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-289">For the page **Choose info you want this label applied to**: Select one of the templates, such as **Financial** or **Privacy**.</span></span> <span data-ttu-id="c36b5-290">ドロップダウンの**表示オプション**を使用して、検索を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-290">You can refine your search by using the **Show options for** dropdown.</span></span> <span data-ttu-id="c36b5-291">または、テンプレートが要件を満たしていない場合は、[**カスタム ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-291">Or, select **Custom policy** if the templates don't meet your requirements.</span></span> <span data-ttu-id="c36b5-292">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-292">Select **Next**.</span></span>

5. <span data-ttu-id="c36b5-293">[**自動ラベル ポリシーに名前を付ける**] ページの場合: 一意の名前を入力し、必要に応じて説明を入力して、自動的に適用されるラベル、場所、ラベル付けするコンテンツを識別する条件を識別します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-293">For the page **Name your auto-labeling policy**: Provide a unique name, and optionally a description to help identify the automatically applied label, locations, and conditions that identify the content to label.</span></span>

6. <span data-ttu-id="c36b5-294">[**ラベルを適用する場所を選択する**] ページの場合: Exchange、SharePoint サイト、OneDrive の場所を選択して指定します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-294">For the page **Choose locations where you want to apply the label**: Select and specify locations for Exchange, SharePoint sites, and OneDrive.</span></span> <span data-ttu-id="c36b5-295">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-295">Then select **Next**.</span></span>

7. <span data-ttu-id="c36b5-296">[**ポリシーの設定を定義する**] ページの場合: 既定の**次を含むコンテンツを検索**のままにして、選択したすべての場所でラベル付けするコンテンツを識別するルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-296">For the **Define policy settings** page: Keep the default of **Find content that contains** to define rules that identify content to label across all your selected locations.</span></span> <span data-ttu-id="c36b5-297">場所ごとに異なるルールが必要な場合は、[**詳細設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-297">If you need different rules per location, select **Advanced settings**.</span></span> <span data-ttu-id="c36b5-298">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-298">Then select **Next**.</span></span>
    
    <span data-ttu-id="c36b5-299">ルールでは、機密情報の種類と共有オプションを含む条件を使用します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-299">The rules use conditions that include sensitive information types and sharing options:</span></span>
    - <span data-ttu-id="c36b5-300">機密情報の種類については、組み込みとカスタムの両方の機密情報の種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-300">For sensitive information types, you can select both built-in and custom sensitive information types.</span></span>
    - <span data-ttu-id="c36b5-301">共有オプションについては、[**組織内の連絡先のみ**] または [**組織外の連絡先**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-301">For the shared options, you can choose **only with people inside my organization** or **with people outside my organization**.</span></span>
    
    <span data-ttu-id="c36b5-302">唯一の場所が **Exchange** である場合、または [**詳細設定**] を選択した場合、次のような選択ができる追加の条件があります。</span><span class="sxs-lookup"><span data-stu-id="c36b5-302">If your only location is **Exchange**, or if you select **Advanced settings**, there are additional conditions that you can select:</span></span>
    - <span data-ttu-id="c36b5-303">送信者の IP アドレスが</span><span class="sxs-lookup"><span data-stu-id="c36b5-303">Sender IP address is</span></span>
    - <span data-ttu-id="c36b5-304">受信者ドメインが</span><span class="sxs-lookup"><span data-stu-id="c36b5-304">Recipient domain is</span></span>
    - <span data-ttu-id="c36b5-305">受信者が</span><span class="sxs-lookup"><span data-stu-id="c36b5-305">Recipient is</span></span>
    - <span data-ttu-id="c36b5-306">添付ファイルの拡張子が</span><span class="sxs-lookup"><span data-stu-id="c36b5-306">Attachment's file extension is</span></span>
    - <span data-ttu-id="c36b5-307">添付ファイルがパスワードで保護されている</span><span class="sxs-lookup"><span data-stu-id="c36b5-307">Attachment is password protected</span></span>
    - <span data-ttu-id="c36b5-308">メールの添付ファイルのコンテンツをスキャンできなかった</span><span class="sxs-lookup"><span data-stu-id="c36b5-308">Any email attachment's content could not be scanned</span></span>
    - <span data-ttu-id="c36b5-309">メールの添付ファイルのコンテンツのスキャンが完了しなかった</span><span class="sxs-lookup"><span data-stu-id="c36b5-309">Any email attachment's content didn't complete scanning</span></span>

8. <span data-ttu-id="c36b5-310">[**ラベルを付けるコンテンツを定義するルールを設定する**] ページの場合: [**+ ルールの作成**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-310">For the **Set up rules to define what content is labeled** page: Select **+ Create rule** and then select **Next**.</span></span>

9. <span data-ttu-id="c36b5-311">[**ルールの作成**] ページで、機密情報の種類または共有オプションを使用してルールに名前を付けて定義して、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-311">On the **Create rule** page, name and define your rule, using sensitive information types or the sharing option, and then select **Save**.</span></span>
    
    <span data-ttu-id="c36b5-312">機密情報の種類の構成オプションは、Office アプリの自動ラベル付けに選択したものと同じです。</span><span class="sxs-lookup"><span data-stu-id="c36b5-312">The configuration options for sensitive information types are the same as those you select for auto-labeling for Office apps.</span></span> <span data-ttu-id="c36b5-313">詳細情報が必要な場合は、「[ラベルの機密情報の種類の構成](#configuring-sensitive-info-types-for-a-label)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c36b5-313">If you need more information, see [Configuring sensitive info types for a label](#configuring-sensitive-info-types-for-a-label).</span></span>

10. <span data-ttu-id="c36b5-314">[**ルールを設定して、ラベル付けするコンテンツを定義する**] ページに戻ります。ラベルを付けるコンテンツを特定する別のルールが必要な場合は、[**+ ルールの作成**] をもう一度選択し、前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-314">Back on the **Set up rules to define what content is labeled** page: Select **+ Create rule** again if you need another rule to identify the content to label, and repeat the previous step.</span></span> <span data-ttu-id="c36b5-315">必要なすべてのルールを定義し、状態が [オン] になっていることを確認したら、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-315">When you have defined all the rules you need, and confirmed their status is on, select **Next**.</span></span>

11. <span data-ttu-id="c36b5-316">[**自動適用するラベルを選択する**] ページの場合: [**+ ラベルの選択**] を選択し、[**機密ラベルの選択**] ウィンドウのラベルを選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-316">For the **Choose a label to auto-apply** page: Select **+ Choose a label**, select a label from the **Choose a sensitivity label** pane, and then select **Next**.</span></span>

12. <span data-ttu-id="c36b5-317">**[ポリシー シミュレーションを今すぐ実行するか、後で実行するかを決定する]** ページの場合: シミュレーション モードで、今すぐ自動ラベル付けポリシーを実行する準備が整っている場合は、**[シミュレーション モードでポリシーを実行する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-317">For the **Decide if you want to run policy simulation now or later** page: Select **Run policy in simulation mode** if you're ready to run the auto-labeling policy now, in simulation mode.</span></span> <span data-ttu-id="c36b5-318">それ以外の場合は、**[ポリシーをオフのままにする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-318">Otherwise, select **Leave policy turned off**.</span></span> <span data-ttu-id="c36b5-319">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-319">Select **Next**.</span></span> 

13. <span data-ttu-id="c36b5-320">[**概要**] ページの場合: 自動ラベル付けポリシーの構成を確認し、必要な変更を行い、ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-320">For the **Summary** page: Review the configuration of the your auto-labeling policy and make any changes that needed, and complete the wizard.</span></span>
    
    <span data-ttu-id="c36b5-321">Office アプリの自動ラベル付けとは異なり、個別の公開オプションはありません。</span><span class="sxs-lookup"><span data-stu-id="c36b5-321">Unlike auto-labeling for Office apps, there's no separate publish option.</span></span> <span data-ttu-id="c36b5-322">ただし、ラベルの公開と同様に、自動ラベル付けポリシーが組織全体に複製されるまでに最大 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="c36b5-322">However, as with publishing labels, allow up to 24 hours for the auto-labeling policy to replicate throughout your organization.</span></span>

<span data-ttu-id="c36b5-323">**[情報保護]** ページの **[自動ラベル付け (プレビュー)]** タブでは、自動ラベル付けポリシーを **[シミュレーション]** または **[オフ]** セクションのどちらかで確認できます。これは、シミュレーション モードで実行することを選択したかどうかによって決まります。</span><span class="sxs-lookup"><span data-stu-id="c36b5-323">Now on the **Information protection** page, **Auto-labeling (preview)** tab, you see your auto-labeling policy in the **Simulation** or **Off** section, depending on whether you chose to run it in simulation mode or not.</span></span> <span data-ttu-id="c36b5-324">ポリシーを選択して、構成と状態の詳細 (**[ポリシー シミュレーションの実行中]** など) を確認します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-324">Select your policy to see the details of the configuration and status (for example, **Policy simulation is still running**).</span></span> <span data-ttu-id="c36b5-325">シミュレーション モードのポリシーの場合は、**[一致したアイテム]** タブを選択して、指定したルールに一致した電子メールまたはドキュメントを確認します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-325">For policies in simulation mode, select the **Matched items** tab to see which emails or documents matched the rules that you specified.</span></span>

<span data-ttu-id="c36b5-326">このインターフェイスからは、次のようにポリシーを直接変更できます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-326">You can modify your policy directly from this interface:</span></span>

- <span data-ttu-id="c36b5-327">**[オフ]** セクションのポリシーの場合は、**[ポリシーの編集]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-327">For a policy in the **Off** section, select the **Edit policy** button.</span></span>

- <span data-ttu-id="c36b5-328">**[シミュレーション]** セクションのポリシーの場合は、いずれかのタブからページの上部にある **[編集]** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-328">For policy in the **Simulation** section, select the **Edit** option at the top of the page, from either tab:</span></span>
    
    ![自動ラベル付けポリシーの編集オプション](../media/auto-labeling-edit.png)
    
    <span data-ttu-id="c36b5-330">シミュレーションなしでポリシーを実行する準備が整っているときには、**[ポリシーを有効にする]** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c36b5-330">When you're ready to run the policy without simulation, select the **Turn on policy** option.</span></span>

<span data-ttu-id="c36b5-331">また、適切な[アクセス許可](data-classification-content-explorer.md#permissions)がある場合は、[コンテンツ エクスプローラー](data-classification-content-explorer.md)を使用して、自動ラベル付けポリシーの結果を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-331">You can also see the results of your auto-labeling policy by using [content explorer](data-classification-content-explorer.md) when you have the appropriate [permissions](data-classification-content-explorer.md#permissions):</span></span>
- <span data-ttu-id="c36b5-332">**コンテンツ エクスプローラー リスト ビューアー**では、ファイルのラベルは表示できますが、ファイルのコンテンツは表示できません。</span><span class="sxs-lookup"><span data-stu-id="c36b5-332">**Content Explorer List viewer** lets you see a file's label but not the file's contents.</span></span>
- <span data-ttu-id="c36b5-333">**コンテンツ エクスプローラー コンテンツ ビューアー**では、ファイルの内容を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-333">**Content Explorer Content viewer** lets you see the file's contents.</span></span>

> [!TIP]
> <span data-ttu-id="c36b5-334">コンテンツ エクスプローラーを使用して、機密情報を含むラベルの付いていないドキュメントがある場所を特定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-334">You can also use content explorer to identify locations that have unlabeled documents that contain sensitive information.</span></span> <span data-ttu-id="c36b5-335">この情報を使用して、自動ラベル付けポリシーにこれらの場所を追加することを検討し、識別された機密情報の種類をルールとして含めます。</span><span class="sxs-lookup"><span data-stu-id="c36b5-335">Using this information, consider adding these locations to your auto-labeling policy, and include the identified sensitive information types as rules.</span></span>

