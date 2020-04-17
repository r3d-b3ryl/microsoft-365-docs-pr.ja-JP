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
ms.openlocfilehash: 4ce9e06bb98fb391bb9eb5ffa01491e0c85eba1f
ms.sourcegitcommit: 4ddbc1c3c29d79d3c4640b7b32f95576784efcca
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240302"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="876e3-103">機密ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="876e3-103">Apply a sensitivity label to content automatically</span></span>

><span data-ttu-id="876e3-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="876e3-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="876e3-105">機密ラベルを作成する場合、指定した条件に一致したときに、そのラベルをコンテンツに自動的に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="876e3-105">When you create a sensitivity label, you can automatically assign that label to content when it matches conditions that you specify.</span></span>

<span data-ttu-id="876e3-106">機密ラベルを自動的にコンテンツに適用する機能が重要である理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="876e3-106">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="876e3-107">ユーザーのトレーニングは、一部の分類方法をいつ使用するかについてのみ必要。</span><span class="sxs-lookup"><span data-stu-id="876e3-107">You don't need to train your users when to use each of your classifications.</span></span>

- <span data-ttu-id="876e3-108">ユーザーへの依存は、一部のコンテンツを正しく分類するためにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="876e3-108">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="876e3-109">ユーザーはポリシーについて把握する必要がなくなり、自分たちの仕事に集中できます。</span><span class="sxs-lookup"><span data-stu-id="876e3-109">Users no longer need to know about your policies — they can instead focus on their work.</span></span>

<span data-ttu-id="876e3-110">機密ラベルを自動的に適用するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="876e3-110">There are two different methods for automatically applying a sensitivity label:</span></span>

- <span data-ttu-id="876e3-111">**ユーザーがドキュメントを編集したり、メールを作成 (返信または転送) するときのクライアント側のラベル付け**: Office アプリ (Word、Excel、PowerPoint、Outlook) の自動ラベル付け用に構成されたラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="876e3-111">**Client-side labeling when users edit documents or compose (also reply or forward) emails**: Use a label that's configured for auto-labeling for Office apps (Word, Excel, PowerPoint, and Outlook).</span></span> 
    
    <span data-ttu-id="876e3-112">この方法は、ユーザーへのラベルの推奨と、ラベルの自動適用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="876e3-112">This method supports recommending a label to users, as well as automatically applying a label.</span></span> <span data-ttu-id="876e3-113">ただし、どちらの場合も、ユーザーはラベルを承諾または拒否するかどうかを決定し、コンテンツの正しいラベル付けを行います。</span><span class="sxs-lookup"><span data-stu-id="876e3-113">But in both cases, the user decides whether to accept or reject the label, to help ensure the correct labeling of content.</span></span> <span data-ttu-id="876e3-114">このクライアント側のラベル付けでは、ドキュメントを保存する前であってもラベルを適用できるため、ドキュメントの遅延が最小限に抑えられます。</span><span class="sxs-lookup"><span data-stu-id="876e3-114">This client-side labeling has minimal delay for documents because the label can be applied even before the document is saved.</span></span> <span data-ttu-id="876e3-115">ただし、すべてのクライアント アプリが自動ラベル付けをサポートしているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="876e3-115">However, not all client apps support auto-labeling.</span></span> <span data-ttu-id="876e3-116">この機能は、Azure Information Protection 統合ラベル付けクライアント、および [Office の一部のバージョン](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="876e3-116">This capability is supported by the Azure Information Protection unified labeling client, and [some versions of Office](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span> 
    
    <span data-ttu-id="876e3-117">構成手順については、このページの「[Office アプリの自動ラベル付けを構成する方法](#how-to-configure-auto-labeling-for-office-apps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="876e3-117">For configuration instructions, see [How to configure auto-labeling for Office apps](#how-to-configure-auto-labeling-for-office-apps) on this page.</span></span>

- <span data-ttu-id="876e3-118">**コンテンツが既に保存されている (SharePoint Online または OneDrive for Business で) またはメールで送信された (Exchange Online によって処理される) サービス側のラベル付け**: 自動ラベル付けポリシーを使用します (現在プレビュー中)。</span><span class="sxs-lookup"><span data-stu-id="876e3-118">**Service-side labeling when content is already saved (in SharePoint Online or OneDrive for Business) or emailed (processed by Exchange Online)**: Use an auto-labeling policy—currently in preview.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="876e3-119">プレビューのお知らせ、「[Microsoft 365 サービスの機密ラベルを使用した自動分類のパブリック プレビューの発表](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-public-preview-of-auto-classification-with/ba-p/1279961)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="876e3-119">See the preview announcement, [Announcing public preview of auto classification with sensitivity labels in Microsoft 365 services](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-public-preview-of-auto-classification-with/ba-p/1279961).</span></span>
    
    <span data-ttu-id="876e3-120">この方法は、機密ラベルを使用した自動分類と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="876e3-120">This method is referred to as auto classification with sensitivity labels.</span></span> <span data-ttu-id="876e3-121">また、保存データ (SharePoint および OneDrive のドキュメント) や転送中のデータ (Exchange によって送信または受信されたメール) の自動ラベル付けと呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="876e3-121">You might also hear it referred to as auto-labeling for data at rest (documents in SharePoint and OneDrive) and data in transit (email that is sent or received by Exchange).</span></span> <span data-ttu-id="876e3-122">Exchange の場合、保存されているメール (メールボックス) は含まれません。</span><span class="sxs-lookup"><span data-stu-id="876e3-122">For Exchange, it doesn't include emails at rest (mailboxes).</span></span> 
    
    <span data-ttu-id="876e3-123">このラベル付けはアプリケーションではなくサービスによって適用されるため、ユーザーが使用しているアプリやバージョンを気にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="876e3-123">Because this labeling is applied by services rather than by applications, you don't need to worry about what apps users have and what version.</span></span> <span data-ttu-id="876e3-124">その結果、この機能は、組織全体ですぐに使用できるようになります。また、規模に応じたラベル付けに適しています。</span><span class="sxs-lookup"><span data-stu-id="876e3-124">As a result, this capability is immediately available throughout your organization and suitable for labeling at scale.</span></span> <span data-ttu-id="876e3-125">自動ラベル付けポリシーでは、ユーザーがラベル付けプロセスを操作しないので、推奨されるラベル付けをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="876e3-125">Auto-labeling policies don't support recommended labeling because the user doesn't interact with the labeling process.</span></span> <span data-ttu-id="876e3-126">代わりに、管理者は、実際にラベルを適用する前に、コンテンツの正しいラベル付けを行うために、シミュレーション モードでポリシーを実行します。</span><span class="sxs-lookup"><span data-stu-id="876e3-126">Instead, the administrator runs the policies in simulation mode to help ensure the correct labeling of content before actually applying the label.</span></span>
    
    <span data-ttu-id="876e3-127">構成手順については、このページの「[SharePoint、OneDrive、Exchange の自動ラベル付けポリシーを構成する方法](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="876e3-127">For configuration instructions, see [How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) on this page.</span></span>
    
    <span data-ttu-id="876e3-128">SharePoint と OneDrive の自動ラベル付けに固有:</span><span class="sxs-lookup"><span data-stu-id="876e3-128">Specific to auto-labeling for SharePoint and OneDrive:</span></span>
    - <span data-ttu-id="876e3-129">テナント内で 1 日あたり最大 25,000 個の自動的にラベル付けされたファイル (Word、PowerPoint、または Excel)</span><span class="sxs-lookup"><span data-stu-id="876e3-129">Maximum of 25,000 automatically labeled files (Word, PowerPoint, or Excel) in your tenant per day</span></span>
        - <span data-ttu-id="876e3-130">ライセンスが割り当てられたユーザー 1 人につき 1 日あたり最大 5 つの自動的にラベル付けされたファイル</span><span class="sxs-lookup"><span data-stu-id="876e3-130">Maximum of 5 automatically labeled files per licensed user per day</span></span>
    - <span data-ttu-id="876e3-131">すべてのポリシー全体で最大 10 のサイト コレクション</span><span class="sxs-lookup"><span data-stu-id="876e3-131">Maximum of 10 sites collections across all policies</span></span>
    - <span data-ttu-id="876e3-132">テナント全体で最大 10 のポリシー</span><span class="sxs-lookup"><span data-stu-id="876e3-132">Maximum of 10 policies across your tenant</span></span>

    <span data-ttu-id="876e3-133">Exchange の自動ラベル付けに固有:</span><span class="sxs-lookup"><span data-stu-id="876e3-133">Specific to auto-labeling for Exchange:</span></span>
    - <span data-ttu-id="876e3-134">手動でのラベル付けや Office アプリを使用した自動ラベル付けとは異なり、Office の添付ファイルも自動ラベル付けポリシーで指定した条件に合わせてスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="876e3-134">Unlike manual labeling or auto-labeling with Office apps, Office attachments are also scanned for the conditions you specify in your auto-labeling policy.</span></span> <span data-ttu-id="876e3-135">一致がある場合、メールにはラベルが付けられますが、添付ファイルにはラベルが付けられません。</span><span class="sxs-lookup"><span data-stu-id="876e3-135">When there is a match, the email is labeled but not the attachment.</span></span>
    - <span data-ttu-id="876e3-136">IRM 暗号化を適用する Exchange メール フロー ルールまたはデータ損失防止 (DLP) ポリシーがある場合: これらのルールやポリシーおよび自動ラベル付けポリシーによってコンテンツが識別されると、ラベルが適用されます。</span><span class="sxs-lookup"><span data-stu-id="876e3-136">If you have Exchange mail flow rules or data loss prevention (DLP) policies that apply IRM encryption: When content is identified by these rules or policies and an auto-labeling policy, the label is applied.</span></span> <span data-ttu-id="876e3-137">このラベルが暗号化を適用すると、Exchange メール フロー ルールまたは DLP ポリシーの IRM 設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="876e3-137">If that label applies encryption, the IRM settings from the Exchange mail flow rules or DLP policies are ignored.</span></span> <span data-ttu-id="876e3-138">ただし、そのラベルが暗号化を適用しない場合、メール フロー ルールまたは DLP ポリシーの IRM 設定がラベルに加えて適用されます。</span><span class="sxs-lookup"><span data-stu-id="876e3-138">However, if that label doesn't apply encryption, the IRM settings from the mail flow rules or DLP policies are applied in addition to the label.</span></span>
    - <span data-ttu-id="876e3-139">ラベルが表示されない IRM 暗号化を使用しているメールは、自動ラベル付けを使用すると一致する場合は、暗号化設定のあるラベルに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="876e3-139">Email that has IRM encryption with no label will be replaced by a label with any encryption settings when there is a match by using auto-labeling.</span></span>
    - <span data-ttu-id="876e3-140">自動ラベル付け条件と一致すると、受信メールにラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="876e3-140">Incoming email is labeled when there is a match with your auto-labeling conditions.</span></span> <span data-ttu-id="876e3-141">ただし、ラベルが暗号化用に構成されている場合、その暗号化は適用されません。</span><span class="sxs-lookup"><span data-stu-id="876e3-141">However, if the label is configured for encryption, that encryption isn't applied.</span></span>
    

## <a name="compare-auto-labeling-for-office-apps-with-auto-labeling-policies"></a><span data-ttu-id="876e3-142">Office アプリの自動ラベル付けと自動ラベル付けポリシーを比較する</span><span class="sxs-lookup"><span data-stu-id="876e3-142">Compare auto-labeling for Office apps with auto-labeling policies</span></span>

<span data-ttu-id="876e3-143">次の表は、2 つの相補的な自動ラベル付け方法の違いを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="876e3-143">Use the following table to help you identify the differences in behavior for the two complementary automatic labeling methods:</span></span>

|<span data-ttu-id="876e3-144">機能または動作</span><span class="sxs-lookup"><span data-stu-id="876e3-144">Feature or behavior</span></span>|<span data-ttu-id="876e3-145">ラベル設定: Office アプリの自動ラベル付け</span><span class="sxs-lookup"><span data-stu-id="876e3-145">Label setting: Auto-labeling for Office apps</span></span> |<span data-ttu-id="876e3-146">ポリシー: 自動ラベル付け</span><span class="sxs-lookup"><span data-stu-id="876e3-146">Policy: Auto-labeling</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="876e3-147">アプリの依存関係</span><span class="sxs-lookup"><span data-stu-id="876e3-147">App dependency</span></span>|[<span data-ttu-id="876e3-148">はい</span><span class="sxs-lookup"><span data-stu-id="876e3-148">Yes</span></span>](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) |<span data-ttu-id="876e3-149">いいえ</span><span class="sxs-lookup"><span data-stu-id="876e3-149">No</span></span> |
|<span data-ttu-id="876e3-150">場所による制限</span><span class="sxs-lookup"><span data-stu-id="876e3-150">Restrict by location</span></span>|<span data-ttu-id="876e3-151">いいえ</span><span class="sxs-lookup"><span data-stu-id="876e3-151">No</span></span> |<span data-ttu-id="876e3-152">はい</span><span class="sxs-lookup"><span data-stu-id="876e3-152">Yes</span></span> |
|<span data-ttu-id="876e3-153">条件: トレーニング可能な分類子</span><span class="sxs-lookup"><span data-stu-id="876e3-153">Conditions: Trainable classifers</span></span>|<span data-ttu-id="876e3-154">はい (制限付きプレビュー)</span><span class="sxs-lookup"><span data-stu-id="876e3-154">Yes (limited preview)</span></span> |<span data-ttu-id="876e3-155">いいえ</span><span class="sxs-lookup"><span data-stu-id="876e3-155">No</span></span> |
|<span data-ttu-id="876e3-156">条件: メールの共有オプションと追加オプション</span><span class="sxs-lookup"><span data-stu-id="876e3-156">Conditions: Sharing options and additional options for email</span></span>|<span data-ttu-id="876e3-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="876e3-157">No</span></span> |<span data-ttu-id="876e3-158">はい</span><span class="sxs-lookup"><span data-stu-id="876e3-158">Yes</span></span> |
|<span data-ttu-id="876e3-159">推奨事項、ポリシーのヒント、ユーザー上書き</span><span class="sxs-lookup"><span data-stu-id="876e3-159">Recommendations, policy tooltip, and user overrides</span></span>|<span data-ttu-id="876e3-160">はい</span><span class="sxs-lookup"><span data-stu-id="876e3-160">Yes</span></span> |<span data-ttu-id="876e3-161">いいえ</span><span class="sxs-lookup"><span data-stu-id="876e3-161">No</span></span> |
|<span data-ttu-id="876e3-162">シミュレーション モード</span><span class="sxs-lookup"><span data-stu-id="876e3-162">Simulation mode</span></span>|<span data-ttu-id="876e3-163">いいえ</span><span class="sxs-lookup"><span data-stu-id="876e3-163">No</span></span> |<span data-ttu-id="876e3-164">はい</span><span class="sxs-lookup"><span data-stu-id="876e3-164">Yes</span></span> |
|<span data-ttu-id="876e3-165">条件についてチェックされた Exchange 添付ファイル</span><span class="sxs-lookup"><span data-stu-id="876e3-165">Exchange attachments checked for conditions</span></span>|<span data-ttu-id="876e3-166">いいえ</span><span class="sxs-lookup"><span data-stu-id="876e3-166">No</span></span> | <span data-ttu-id="876e3-167">はい</span><span class="sxs-lookup"><span data-stu-id="876e3-167">Yes</span></span>|
|<span data-ttu-id="876e3-168">視覚的なマーキングの適用</span><span class="sxs-lookup"><span data-stu-id="876e3-168">Apply visual markings</span></span> |<span data-ttu-id="876e3-169">はい</span><span class="sxs-lookup"><span data-stu-id="876e3-169">Yes</span></span> |<span data-ttu-id="876e3-170">はい (メール専用)</span><span class="sxs-lookup"><span data-stu-id="876e3-170">Yes (email only)</span></span> |
|<span data-ttu-id="876e3-171">ラベルなしで適用された IRM 暗号化の上書き</span><span class="sxs-lookup"><span data-stu-id="876e3-171">Override IRM encryption applied without a label</span></span>|<span data-ttu-id="876e3-172">はい (ユーザーがエクスポートの最小使用権を持っている場合)</span><span class="sxs-lookup"><span data-stu-id="876e3-172">Yes if the user has the minimum usage right of Export</span></span> |<span data-ttu-id="876e3-173">はい (メール専用)</span><span class="sxs-lookup"><span data-stu-id="876e3-173">Yes (email only)</span></span> |
|<span data-ttu-id="876e3-174">受信メールのラベル付け</span><span class="sxs-lookup"><span data-stu-id="876e3-174">Label incoming email</span></span>|<span data-ttu-id="876e3-175">いいえ</span><span class="sxs-lookup"><span data-stu-id="876e3-175">No</span></span> |<span data-ttu-id="876e3-176">はい (暗号化は適用されません)</span><span class="sxs-lookup"><span data-stu-id="876e3-176">Yes (encryption not applied)</span></span> |

> [!NOTE]
> <span data-ttu-id="876e3-177">コンテンツが手動でラベル付けされている場合、そのラベルが自動ラベル付けに置き換えられることはありません。</span><span class="sxs-lookup"><span data-stu-id="876e3-177">When content has been manually labeled, that label will never be replaced by automatic labeling.</span></span> <span data-ttu-id="876e3-178">ただし、自動ラベル付けポリシーは、Office アプリの自動ラベル付けを使用して適用された[優先度の低いラベル](sensitivity-labels.md#label-priority-order-matters)を置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="876e3-178">However, auto-labeling policies can replace a [lower priority label](sensitivity-labels.md#label-priority-order-matters) that was applied by using auto-labeling for Office apps.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="876e3-179">複数のラベルに適用するときの複数の条件の評価方法</span><span class="sxs-lookup"><span data-stu-id="876e3-179">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="876e3-p108">ラベルは、ポリシー内で指定した位置に従って評価の順序を決められます。先頭に配置したラベルが最下位 (機密性が最も低い) になり、最後に配置したラベルが最上位 (機密性が最も高い) になります。優先度に関する詳細については、「[ラベルの優先度 (順序の問題)](sensitivity-labels.md#label-priority-order-matters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="876e3-p108">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="876e3-182">自動適用または推奨されるように親ラベルを構成しない</span><span class="sxs-lookup"><span data-stu-id="876e3-182">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="876e3-183">親ラベル (サブラベルのあるラベル) はコンテンツに適用できません。</span><span class="sxs-lookup"><span data-stu-id="876e3-183">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="876e3-184">Office アプリで親ラベルが自動適用または自動推奨されるように構成されていないこと、自動ラベル ポリシーで親ラベルが選択されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="876e3-184">Make sure that you don't configure a parent label to be auto-applied or recommended in Office apps, and don't select a parent label for an auto-labeling policy.</span></span> <span data-ttu-id="876e3-185">その場合、親ラベルをコンテンツに適用できなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="876e3-185">If you do, the parent label won't be applied to content.</span></span>

<span data-ttu-id="876e3-186">自動ラベルでサブラベルも使用するには、必ず親ラベルとサブラベルの両方を発行してください。</span><span class="sxs-lookup"><span data-stu-id="876e3-186">To use automatic labeling with sublabels, make sure you publish both the parent label and the sublabel.</span></span>

<span data-ttu-id="876e3-187">親ラベルとサブラベルの詳細については、「[サブラベル (ラベルのグループ化)](sensitivity-labels.md#sublabels-grouping-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="876e3-187">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>

## <a name="how-to-configure-auto-labeling-for-office-apps"></a><span data-ttu-id="876e3-188">Office アプリの自動ラベル付けを構成する方法</span><span class="sxs-lookup"><span data-stu-id="876e3-188">How to configure auto-labeling for Office apps</span></span>

<span data-ttu-id="876e3-189">Windows 用 Office アプリの自動ラベル付けは、Azure Information Protection 統合ラベル付けクライアントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="876e3-189">Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="876e3-190">Office アプリ組み込みのラベル付けでは、この機能が[一部のアプリでプレビュー](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)されています。</span><span class="sxs-lookup"><span data-stu-id="876e3-190">For built-in labeling in Office apps, this capability is [in preview for some apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

<span data-ttu-id="876e3-191">Office アプリの自動ラベル付け設定は、[機密ラベルを作成または編集する](create-sensitivity-labels.md)ときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="876e3-191">The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md):</span></span>

![機密ラベルの自動ラベル付けオプション](../media/sensitivity-labels-auto-labeling-options.png)

<span data-ttu-id="876e3-193">コンテンツに特定の種類の機密情報が含まれている場合、機密ラベルをコンテンツに自動的に適用することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="876e3-193">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information.</span></span> <span data-ttu-id="876e3-194">機密情報の種類または分類子のリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="876e3-194">Choose from a list of sensitive info types or classifers:</span></span>

![Office アプリの自動ラベル付けのラベル条件](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> <span data-ttu-id="876e3-196">現在、**分類子** のオプションは制限付きプレビュー中であり、テナントでこの機能を有効にするには Microsoft にフォームを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="876e3-196">Currently, the option for **Classifers** is in limited preview and requires you to submit a form to Microsoft to enable this capability for your tenant.</span></span> <span data-ttu-id="876e3-197">詳細については、「[Announcing automatic labeling in Office Apps using built-in classifiers - Limited Preview (組み込みの分類子を使用した Office アプリの自動ラベル付けの発表 - 制限付きプレビュー)](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889)」のブログ投稿を参照してください。</span><span class="sxs-lookup"><span data-stu-id="876e3-197">For more information, see the blog post [Announcing automatic labeling in Office Apps using built-in classifiers - Limited Preview](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span></span>

<span data-ttu-id="876e3-198">この機密ラベルが自動的に適用されると、ユーザーの Office アプリに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="876e3-198">When this sensitivity label is automatically applied, the user sees a notification in their Office app.</span></span> <span data-ttu-id="876e3-199">例:</span><span class="sxs-lookup"><span data-stu-id="876e3-199">For example:</span></span>

![ドキュメントにラベルが自動適用されたという通知](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a><span data-ttu-id="876e3-201">ラベルの機密情報の種類の構成</span><span class="sxs-lookup"><span data-stu-id="876e3-201">Configuring sensitive info types for a label</span></span>

<span data-ttu-id="876e3-202">**機密情報の種類** オプションを選択すると、データ損失防止 (DLP) ポリシーを作成するときと同じ機密情報の種類の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="876e3-202">When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="876e3-203">そのため、たとえば、クレジットカード番号や社会保障番号など、お客様の個人情報 (PII) を含むコンテンツに極秘ラベルを自動的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="876e3-203">So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers:</span></span>

![Officeアプリの自動ラベル付け用の機密情報の種類](../media/sensitivity-labels-sensitive-info-types.png)

<span data-ttu-id="876e3-205">機密情報の種類を選択した後は、インスタンス数または一致精度を変更して条件を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="876e3-205">After you select your sensitive information types, you can refine your condition by changing the instance count or match accuracy.</span></span> <span data-ttu-id="876e3-206">詳細については、「[一致の難易度を設定するためのルールの調整](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="876e3-206">For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="876e3-207">さらに、条件で検知する必要があるのは、機密情報の種類のすべてか、またはそのうちの 1 つだけかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="876e3-207">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="876e3-208">また、条件をより柔軟または複雑にするには、グループを追加し、グループ間で論理演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="876e3-208">And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups.</span></span> <span data-ttu-id="876e3-209">詳細については、「[グループ化および論理演算子](data-loss-prevention-policies.md#grouping-and-logical-operators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="876e3-209">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

![インスタンス数と一致精度のオプション](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifers-for-a-label"></a><span data-ttu-id="876e3-211">ラベルの分類子の構成</span><span class="sxs-lookup"><span data-stu-id="876e3-211">Configuring classifers for a label</span></span>

<span data-ttu-id="876e3-212">**分類子** オプションを選択する場合、1 つ以上の組み込み分類子を選択します。</span><span class="sxs-lookup"><span data-stu-id="876e3-212">When you select the **Classifers** option, select one or more of the built-in classifiers:</span></span>

![分類子と機密ラベルのオプション](../media/sensitivity-labels-classifers.png)

<span data-ttu-id="876e3-214">それらの分類子の詳細については、「[トレーニング可能な分類子 (プレビュー) の概要](classifier-getting-started-with.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="876e3-214">For more information about these classifers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="876e3-215">プレビュー期間中は、次のアプリが機密ラベルの分類子をサポートします。</span><span class="sxs-lookup"><span data-stu-id="876e3-215">During the preview period, the following apps support classifers for sensitivity labels:</span></span>

- <span data-ttu-id="876e3-216">[Office Insider](https://office.com/insider) の Windows 用 Office 365 ProPlus デスクトップ アプリ:</span><span class="sxs-lookup"><span data-stu-id="876e3-216">Office 365 ProPlus desktop apps for Windows, from [Office Insider](https://office.com/insider):</span></span>
    - <span data-ttu-id="876e3-217">Word</span><span class="sxs-lookup"><span data-stu-id="876e3-217">Word</span></span>
    - <span data-ttu-id="876e3-218">Excel</span><span class="sxs-lookup"><span data-stu-id="876e3-218">Excel</span></span>
    - <span data-ttu-id="876e3-219">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="876e3-219">PowerPoint</span></span>

- <span data-ttu-id="876e3-220">[SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にする機能 (パブリック プレビュー)](sensitivity-labels-sharepoint-onedrive-files.md) が有効になっている場合の Web アプリ用の Office:</span><span class="sxs-lookup"><span data-stu-id="876e3-220">Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    - <span data-ttu-id="876e3-221">Word</span><span class="sxs-lookup"><span data-stu-id="876e3-221">Word</span></span>
    - <span data-ttu-id="876e3-222">Excel</span><span class="sxs-lookup"><span data-stu-id="876e3-222">Excel</span></span>
    - <span data-ttu-id="876e3-223">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="876e3-223">PowerPoint</span></span>
    - <span data-ttu-id="876e3-224">Outlook</span><span class="sxs-lookup"><span data-stu-id="876e3-224">Outlook</span></span>

### <a name="recommend-that-the-user-applies-a-sensitivity-label-in-office-apps"></a><span data-ttu-id="876e3-225">ユーザーが Office アプリで機密ラベルを適用することを推奨</span><span class="sxs-lookup"><span data-stu-id="876e3-225">Recommend that the user applies a sensitivity label in Office apps</span></span>

<span data-ttu-id="876e3-226">状況に応じて、ユーザーがラベルを適用することを推奨できます。</span><span class="sxs-lookup"><span data-stu-id="876e3-226">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="876e3-227">このオプションでは、分類および関連する保護を受け入れるか、またはラベルがそのコンテンツに適していない場合、推奨事項を無視するかをユーザーが選択できます。</span><span class="sxs-lookup"><span data-stu-id="876e3-227">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.</span></span>

![機密ラベルをユーザーに推奨するためのオプション](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="876e3-p118">ラベルを推奨される操作として適用するように条件を構成したときの、Azure Information Protection の統合ラベル付けクライアントからのプロンプトの例を、カスタム ポリシー ヒントと共に示します。ポリシー ヒントに表示するテキストを選択できます。</span><span class="sxs-lookup"><span data-stu-id="876e3-p118">Here's an example of a prompt from the Azure Information Protection unified labeling client when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.</span></span>

![推奨ラベルを適用するためのプロンプト](../media/Sensitivity-label-Prompt-for-required-label.png)

### <a name="when-automatic-or-recommended-labels-are-applied-in-office-apps"></a><span data-ttu-id="876e3-232">Office アプリで自動ラベルまたは推奨ラベルが適用されている場合</span><span class="sxs-lookup"><span data-stu-id="876e3-232">When automatic or recommended labels are applied in Office apps</span></span>

<span data-ttu-id="876e3-233">Office アプリでの自動ラベル付けと推奨ラベル付けの実装は、Office に組み込まれているラベル付けを使用しているか、または Azure Information Protection の統合ラベル付けクライアントを使用しているかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="876e3-233">The implementation of automatic and recommended labeling in Office apps depend on whether you're using labeling that's built into Office, or the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="876e3-234">ただし、どちらの場合も次のようになります。</span><span class="sxs-lookup"><span data-stu-id="876e3-234">In both cases, however:</span></span>

- <span data-ttu-id="876e3-235">以前に手動でラベルが付けられているか、以前に上位の機密度で自動的にラベルが付けられているドキュメントと電子メールには自動ラベル付けを使用できません。</span><span class="sxs-lookup"><span data-stu-id="876e3-235">You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity.</span></span> <span data-ttu-id="876e3-236">ドキュメントや電子メールに適用できる機密ラベルは (1 つの保持ラベルに加えて) 1 つだけであることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="876e3-236">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="876e3-237">以前に上位の秘密度でラベルが付けられているドキュメントまたはメールには推奨ラベル付けを使用できません。</span><span class="sxs-lookup"><span data-stu-id="876e3-237">You can't use recommended labeling for documents or emails that were previously labeled with a higher sensitivity.</span></span> <span data-ttu-id="876e3-238">コンテンツに既に上位の秘密度でラベルが付けられている場合、推奨事項とポリシー ヒントに関するプロンプトは、ユーザーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="876e3-238">When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.</span></span>

<span data-ttu-id="876e3-239">組み込みのラベル付けに関してのみ以下の点が当てはまります。</span><span class="sxs-lookup"><span data-stu-id="876e3-239">Specific to built-in labeling:</span></span>

- <span data-ttu-id="876e3-240">必ずしもすべての Office アプリで自動 (および推奨) ラベル付けがサポートされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="876e3-240">Not all Office apps support automatic (and recommended) labeling.</span></span> <span data-ttu-id="876e3-241">詳しくは、「[アプリでの秘密度ラベル機能のサポート](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="876e3-241">For more information, see [Support for sensitivity label capabilities in apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

- <span data-ttu-id="876e3-242">Word のデスクトップ バージョンにおける推奨ラベルでは、推奨をトリガーした機密コンテンツにフラグが付けられるので、ユーザーが確認して、推奨されている秘密度ラベルを適用しないで機密コンテンツを削除できます。</span><span class="sxs-lookup"><span data-stu-id="876e3-242">For recommended labels in the desktop versions of Word, the sensitive content that triggered the recommendation is flagged so that users can review and remove the sensitive content instead of applying the recommended sensitivity label.</span></span>

- <span data-ttu-id="876e3-243">こうしたラベルが Office アプリで適用される方法、スクリーンショット例、機密情報の検出方法について詳しくは、「[Office のファイルとメールに秘密度ラベルを自動的に適用、または推奨する](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="876e3-243">For details about how these labels are applied in Office apps, example screenshots, and how sensitive information is detected, see [Automatically apply or recommend sensitivity labels to your files and emails in Office](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1).</span></span>

<span data-ttu-id="876e3-244">Azure Information Protection 統合ラベル付けクライアントに関してのみ以下の点が当てはまります。</span><span class="sxs-lookup"><span data-stu-id="876e3-244">Specific to the Azure Information Protection unified labeling client:</span></span>

-  <span data-ttu-id="876e3-245">自動ラベル付けと推奨ラベル付けは、Word、Excel、PowerPoint でドキュメントが保存されるときと、Outlook でメールが送信されるときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="876e3-245">Automatic and recommended labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span>

- <span data-ttu-id="876e3-246">Outlook で推奨ラベル付けをサポートするには、最初に[詳細なポリシー設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook)を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="876e3-246">For Outlook to support recommended labeling, you must first configure an [advanced policy setting](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook).</span></span>

- <span data-ttu-id="876e3-247">ドキュメントやメール内の本文、およびヘッダーとフッターに含まれる機密情報が検出されますが、件名やメールの添付ファイルのものは検知されません。</span><span class="sxs-lookup"><span data-stu-id="876e3-247">Sensitive information can be detected in the body text in documents and emails, and to headers and footers — but not in the subject line or attachments of email.</span></span>

## <a name="how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange"></a><span data-ttu-id="876e3-248">SharePoint、OneDrive、Exchange の自動ラベル付けポリシーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="876e3-248">How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange</span></span>
> [!NOTE]
> <span data-ttu-id="876e3-249">自動ラベル付けポリシーは、パブリック プレビューでテナントに段階的に展開されており、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="876e3-249">Auto-labeling policies are gradually rolling out to tenants in public preview and subject to change.</span></span>

### <a name="prerequisites-for-auto-labeling-policies"></a><span data-ttu-id="876e3-250">自動ラベル付けポリシーの前提条件</span><span class="sxs-lookup"><span data-stu-id="876e3-250">Prerequisites for auto-labeling policies</span></span>

- <span data-ttu-id="876e3-251">シミュレーション モードでは、Office 365 の監査を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="876e3-251">Auditing for Office 365 must be turned on for simulation mode.</span></span> <span data-ttu-id="876e3-252">監査を有効にする必要がある場合、または監査が既に有効になっているかどうかが不明の場合は、「[Office 365 監査ログの検索を有効まは無効にする](turn-audit-log-search-on-or-off.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="876e3-252">If you need to turn on auditing or you're not sure whether auditing is already on, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="876e3-253">SharePoint と OneDrive でファイルに自動でラベルを付けるには:</span><span class="sxs-lookup"><span data-stu-id="876e3-253">To auto-label files in SharePoint and OneDrive:</span></span>
    - <span data-ttu-id="876e3-254">[SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする (パブリック プレビュー)](sensitivity-labels-sharepoint-onedrive-files.md) を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="876e3-254">You have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>
    - <span data-ttu-id="876e3-255">自動ラベル付けポリシーの実行時に、別のプロセスまたはユーザーがファイルを開いておくことはできません。</span><span class="sxs-lookup"><span data-stu-id="876e3-255">At the time the auto-labeling policy runs, the file mustn't be open by another process or user.</span></span>

- <span data-ttu-id="876e3-256">組み込みの機密度の種類ではなく、[カスタムの機密情報の種類](custom-sensitive-info-types.md)を使用する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="876e3-256">If you plan to use [custom sensitive information types](custom-sensitive-info-types.md) rather than the built-in sensitivity types:</span></span> 
    - <span data-ttu-id="876e3-257">カスタムの機密情報の種類は、カスタムの機密情報の種類が保存された後に作成されたコンテンツに対して評価されます。</span><span class="sxs-lookup"><span data-stu-id="876e3-257">Custom sensitivity information types are evaluated for content that is created after the custom sensitivity information types are saved.</span></span> 
    - <span data-ttu-id="876e3-258">新しいカスタムの機密情報の種類をテストするには、自動ラベル付けポリシーを作成する前に作成してから、テスト用のサンプル データを使用して新しいドキュメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="876e3-258">To test new custom sensitive information types, create them before you create your auto-labeling policy, and then create new documents with sample data for testing.</span></span>

- <span data-ttu-id="876e3-259">自動ラベル付けポリシー用に選択できる (少なくとも 1 人のユーザー対して) [作成および公開された](create-sensitivity-labels.md) 1 つ以上の機密ラベル。</span><span class="sxs-lookup"><span data-stu-id="876e3-259">One or more sensitivity labels [created and published](create-sensitivity-labels.md) (to at least one user) that you can select for your auto-labeling policy.</span></span> <span data-ttu-id="876e3-260">これらのラベルの場合:</span><span class="sxs-lookup"><span data-stu-id="876e3-260">For these labels:</span></span>
    - <span data-ttu-id="876e3-261">概要で説明したように、ラベル設定は自動ラベル付けポリシーを補完するため、Office アプリのラベル設定の自動ラベル付けがオンかオフかは関係ありません。</span><span class="sxs-lookup"><span data-stu-id="876e3-261">It doesn't matter if the auto-labeling in Office apps label setting is turned on or off, because that label setting supplements auto-labeling policies, as explained in the introduction.</span></span> 
    - <span data-ttu-id="876e3-262">自動ラベル付けに使用するラベルが視覚的なマーキング (ヘッダー、フッター、透かし) を使用するように構成されている場合、これらはドキュメントに適用されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="876e3-262">If the labels you want to use for auto-labeling are configured to use visual markings (headers, footers, watermarks), note that these are not applied to documents.</span></span>

### <a name="learn-about-simulation-mode"></a><span data-ttu-id="876e3-263">シミュレーション モードの詳細</span><span class="sxs-lookup"><span data-stu-id="876e3-263">Learn about simulation mode</span></span>

<span data-ttu-id="876e3-264">シミュレーション モードは、自動ラベル付けポリシーに固有であり、ワークフローに組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="876e3-264">Simulation mode is unique to auto-labeling policies and woven into the workflow.</span></span> <span data-ttu-id="876e3-265">ポリシーによって少なくとも 1 つのシミュレーションが実行されるまで、ドキュメントとメールに自動的にラベルを付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="876e3-265">You can't automatically label documents and emails until your policy has run at least one simulation.</span></span>

<span data-ttu-id="876e3-266">自動ラベル付けポリシーのワークフロー:</span><span class="sxs-lookup"><span data-stu-id="876e3-266">Workflow for an auto-labeling policy:</span></span>

1. <span data-ttu-id="876e3-267">自動ラベル付けポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="876e3-267">Create and configure an auto-labeling policy</span></span>

2. <span data-ttu-id="876e3-268">シミュレーション モードでポリシーを実行し、少なくとも 24 時間待機する</span><span class="sxs-lookup"><span data-stu-id="876e3-268">Run the policy in simulation mode and wait at least 24 hours</span></span>

3. <span data-ttu-id="876e3-269">結果を確認し、必要に応じてポリシーを調整し、シミュレーション モードを再実行して、少なくとも 24 時間待機する</span><span class="sxs-lookup"><span data-stu-id="876e3-269">Review the results, and if necessary, refine your policy, rerun simulation mode and wait at least 24 hours</span></span>

4. <span data-ttu-id="876e3-270">必要に応じて、手順 3 を繰り返します</span><span class="sxs-lookup"><span data-stu-id="876e3-270">Repeat step 3 as needed</span></span>

5. <span data-ttu-id="876e3-271">本稼働に展開</span><span class="sxs-lookup"><span data-stu-id="876e3-271">Deploy in production</span></span>

<span data-ttu-id="876e3-272">シミュレーションされた展開は、PowerShell の WhatIf パラメーターのように動作します。</span><span class="sxs-lookup"><span data-stu-id="876e3-272">The simulated deployment runs like the WhatIf parameter for PowerShell.</span></span> <span data-ttu-id="876e3-273">定義したルールを使用して、自動ラベル付けポリシーが選択したラベルを適用したかのようにレポートされた結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="876e3-273">You see results reported as if the auto-labeling policy had applied your selected label, using the rules that you defined.</span></span> <span data-ttu-id="876e3-274">その後、必要に応じてルールの精度を高め、シミュレーションを再実行できます。</span><span class="sxs-lookup"><span data-stu-id="876e3-274">You can then refine your rules for accuracy if needed, and rerun the simulation.</span></span> <span data-ttu-id="876e3-275">ただし、Exchange の自動ラベル付けは、メールボックスに保存されたメールではなく、送受信されるメールに適用されるため、完全に同じメール メッセージを送受信することができなければ、シミュレーションのメールの結果に一貫性があるとは期待できません。</span><span class="sxs-lookup"><span data-stu-id="876e3-275">However, because auto-labeling for Exchange applies to emails that are sent and received, rather than emails stored in mailboxes, don't expect results for email in a simulation to be consistent unless you're able to send and receive the exact same email messages.</span></span>

<span data-ttu-id="876e3-276">シミュレーション モードでは、展開前に自動ラベル付けポリシーの範囲を徐々に広げることもできます。</span><span class="sxs-lookup"><span data-stu-id="876e3-276">Simulation mode also lets you gradually increase the scope of your auto-labeling policy before deployment.</span></span> <span data-ttu-id="876e3-277">たとえば、1 つのドキュメント ライブラリを持った SharePoint サイトなどの 1 つの場所から始めることができます。</span><span class="sxs-lookup"><span data-stu-id="876e3-277">For example, you might start with a single location, such as a SharePoint site, with a single document library.</span></span> <span data-ttu-id="876e3-278">次に、反復的な変更を加えて、範囲を複数のサイトに拡大し、次に OneDrive などの別の場所に拡大します。</span><span class="sxs-lookup"><span data-stu-id="876e3-278">Then, with iterative changes, increase the scope to multiple sites, and then to another location, such as OneDrive.</span></span>

<span data-ttu-id="876e3-279">最後に、シミュレーション モードを使用して、自動ラベル付けポリシーの実行に必要な時間の概算を提供し、シミュレーション モードを使用せずに実行するタイミングを計画してスケジュールすることができます。</span><span class="sxs-lookup"><span data-stu-id="876e3-279">Finally, you can use simulation mode to provide an approximation of the time needed to run your auto-labeling policy, to help you plan and schedule when to run it without simulation mode.</span></span>

### <a name="creating-an-auto-labeling-policy"></a><span data-ttu-id="876e3-280">自動ラベル付けポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="876e3-280">Creating an auto-labeling policy</span></span>

1. <span data-ttu-id="876e3-281">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、機密ラベルに移動します。</span><span class="sxs-lookup"><span data-stu-id="876e3-281">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="876e3-282">[**ソリューション**]  >  [**Information Protection**]</span><span class="sxs-lookup"><span data-stu-id="876e3-282">**Solutions** > **Information protection**</span></span>
    
    <span data-ttu-id="876e3-283">このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="876e3-283">If you don't immediately see this option, first select **Show all**.</span></span>

2. <span data-ttu-id="876e3-284">[**自動ラベル付 (プレビュー)**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="876e3-284">Select the **Auto-labeling (preview)** tab:</span></span>
    
    ![自動ラベル付け (プレビュー) タブ](../media/auto-labeling-tab.png)

3. <span data-ttu-id="876e3-286">[**+ ポリシーの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="876e3-286">Select **+ Create policy**.</span></span>

4. <span data-ttu-id="876e3-287">[**このラベルを適用する情報を選択する**] ページの場合: [**財務**] または [**プライバシー**] などのテンプレートのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="876e3-287">For the page **Choose info you want this label applied to**: Select one of the templates, such as **Financial** or **Privacy**.</span></span> <span data-ttu-id="876e3-288">ドロップダウンの**表示オプション**を使用して、検索を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="876e3-288">You can refine your search by using the **Show options for** dropdown.</span></span> <span data-ttu-id="876e3-289">または、テンプレートが要件を満たしていない場合は、[**カスタム ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="876e3-289">Or, select **Custom policy** if the templates don't meet your requirements.</span></span> <span data-ttu-id="876e3-290">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="876e3-290">Select **Next**.</span></span>

5. <span data-ttu-id="876e3-291">[**自動ラベル ポリシーに名前を付ける**] ページの場合: 一意の名前を入力し、必要に応じて説明を入力して、自動的に適用されるラベル、場所、ラベル付けするコンテンツを識別する条件を識別します。</span><span class="sxs-lookup"><span data-stu-id="876e3-291">For the page **Name your auto-labeling policy**: Provide a unique name, and optionally a description to help identify the automatically applied label, locations, and conditions that identify the content to label.</span></span>

6. <span data-ttu-id="876e3-292">[**ラベルを適用する場所を選択する**] ページの場合: Exchange、SharePoint サイト、OneDrive の場所を選択して指定します。</span><span class="sxs-lookup"><span data-stu-id="876e3-292">For the page **Choose locations where you want to apply the label**: Select and specify locations for Exchange, SharePoint sites, and OneDrive.</span></span> <span data-ttu-id="876e3-293">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="876e3-293">Then select **Next**.</span></span>

7. <span data-ttu-id="876e3-294">[**ポリシーの設定を定義する**] ページの場合: 既定の**次を含むコンテンツを検索**のままにして、選択したすべての場所でラベル付けするコンテンツを識別するルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="876e3-294">For the **Define policy settings** page: Keep the default of **Find content that contains** to define rules that identify content to label across all your selected locations.</span></span> <span data-ttu-id="876e3-295">場所ごとに異なるルールが必要な場合は、[**詳細設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="876e3-295">If you need different rules per location, select **Advanced settings**.</span></span> <span data-ttu-id="876e3-296">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="876e3-296">Then select **Next**.</span></span>
    
    <span data-ttu-id="876e3-297">ルールでは、機密情報の種類と共有オプションを含む条件を使用します。</span><span class="sxs-lookup"><span data-stu-id="876e3-297">The rules use conditions that include sensitive information types and sharing options:</span></span>
    - <span data-ttu-id="876e3-298">機密情報の種類については、組み込みとカスタムの両方の機密情報の種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="876e3-298">For sensitive information types, you can select both built-in and custom sensitive information types.</span></span>
    - <span data-ttu-id="876e3-299">共有オプションについては、[**組織内の連絡先のみ**] または [**組織外の連絡先**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="876e3-299">For the shared options, you can choose **only with people inside my organization** or **with people outside my organization**.</span></span>
    
    <span data-ttu-id="876e3-300">唯一の場所が **Exchange** である場合、または [**詳細設定**] を選択した場合、次のような選択ができる追加の条件があります。</span><span class="sxs-lookup"><span data-stu-id="876e3-300">If your only location is **Exchange**, or if you select **Advanced settings**, there are additional conditions that you can select:</span></span>
    - <span data-ttu-id="876e3-301">送信者の IP アドレスが</span><span class="sxs-lookup"><span data-stu-id="876e3-301">Sender IP address is</span></span>
    - <span data-ttu-id="876e3-302">受信者ドメインが</span><span class="sxs-lookup"><span data-stu-id="876e3-302">Recipient domain is</span></span>
    - <span data-ttu-id="876e3-303">受信者が</span><span class="sxs-lookup"><span data-stu-id="876e3-303">Recipient is</span></span>
    - <span data-ttu-id="876e3-304">添付ファイルの拡張子が</span><span class="sxs-lookup"><span data-stu-id="876e3-304">Attachment's file extension is</span></span>
    - <span data-ttu-id="876e3-305">添付ファイルがパスワードで保護されている</span><span class="sxs-lookup"><span data-stu-id="876e3-305">Attachment is password protected</span></span>
    - <span data-ttu-id="876e3-306">文書のプロパティが</span><span class="sxs-lookup"><span data-stu-id="876e3-306">Document property is</span></span>
    - <span data-ttu-id="876e3-307">メールの添付ファイルのコンテンツをスキャンできなかった</span><span class="sxs-lookup"><span data-stu-id="876e3-307">Any email attachment's content could not be scanned</span></span>
    - <span data-ttu-id="876e3-308">メールの添付ファイルのコンテンツのスキャンが完了しなかった</span><span class="sxs-lookup"><span data-stu-id="876e3-308">Any email attachment's content didn't complete scanning</span></span>

8. <span data-ttu-id="876e3-309">[**ラベルを付けるコンテンツを定義するルールを設定する**] ページの場合: [**+ ルールの作成**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="876e3-309">For the **Set up rules to define what content is labeled** page: Select **+ Create rule** and then select **Next**.</span></span>

9. <span data-ttu-id="876e3-310">[**ルールの作成**] ページで、機密情報の種類または共有オプションを使用してルールに名前を付けて定義して、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="876e3-310">On the **Create rule** page, name and define your rule, using sensitive information types or the sharing option, and then select **Save**.</span></span>
    
    <span data-ttu-id="876e3-311">機密情報の種類の構成オプションは、Office アプリの自動ラベル付けに選択したものと同じです。</span><span class="sxs-lookup"><span data-stu-id="876e3-311">The configuration options for sensitive information types are the same as those you select for auto-labeling for Office apps.</span></span> <span data-ttu-id="876e3-312">詳細情報が必要な場合は、「[ラベルの機密情報の種類の構成](#configuring-sensitive-info-types-for-a-label)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="876e3-312">If you need more information, see [Configuring sensitive info types for a label](#configuring-sensitive-info-types-for-a-label).</span></span>

10. <span data-ttu-id="876e3-313">[**ルールを設定して、ラベル付けするコンテンツを定義する**] ページに戻ります。ラベルを付けるコンテンツを特定する別のルールが必要な場合は、[**+ ルールの作成**] をもう一度選択し、前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="876e3-313">Back on the **Set up rules to define what content is labeled** page: Select **+ Create rule** again if you need another rule to identify the content to label, and repeat the previous step.</span></span> <span data-ttu-id="876e3-314">必要なすべてのルールを定義し、状態が [オン] になっていることを確認したら、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="876e3-314">When you have defined all the rules you need, and confirmed their status is on, select **Next**.</span></span>

11. <span data-ttu-id="876e3-315">[**自動適用するラベルを選択する**] ページの場合: [**+ ラベルの選択**] を選択し、[**機密ラベルの選択**] ウィンドウのラベルを選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="876e3-315">For the **Choose a label to auto-apply** page: Select **+ Choose a label**, select a label from the **Choose a sensitivity label** pane, and then select **Next**.</span></span>

12. <span data-ttu-id="876e3-316">[**ポリシーのモードを選択する**] ページの場合: シミュレーション モードで自動ラベル付けポリシーを実行する準備ができている場合は、[**テストを実行する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="876e3-316">For the **Choose a mode for the policy** page: Select **Test it out** if you're ready to run the auto-labeling policy now, in simulation mode.</span></span> <span data-ttu-id="876e3-317">それ以外の場合は、[**オフのままにする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="876e3-317">Otherwise, select **Leave it turned off**.</span></span> <span data-ttu-id="876e3-318">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="876e3-318">Select **Next**.</span></span> 

13. <span data-ttu-id="876e3-319">[**概要**] ページの場合: 自動ラベル付けポリシーの構成を確認し、必要な変更を行い、ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="876e3-319">For the **Summary** page: Review the configuration of the your auto-labeling policy and make any changes that needed, and complete the wizard.</span></span>
    
    <span data-ttu-id="876e3-320">Office アプリの自動ラベル付けとは異なり、個別の公開オプションはありません。</span><span class="sxs-lookup"><span data-stu-id="876e3-320">Unlike auto-labeling for Office apps, there's no separate publish option.</span></span> <span data-ttu-id="876e3-321">ただし、ラベルの公開と同様に、自動ラベル付けポリシーが組織全体に複製されるまでに最大 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="876e3-321">However, as with publishing labels, allow up to 24 hours for the auto-labeling policy to replicate throughout your organization.</span></span>

<span data-ttu-id="876e3-322">これで、[**情報保護**] ページの [**自動ラベル付け (プレビュー)**] タブにある [**テスト**] セクションに、自動ラベル付けポリシーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="876e3-322">Now on the **Information protection** page, **Auto-labeling (preview)** tab, you see your auto-labeling policy in the **Testing** section.</span></span> <span data-ttu-id="876e3-323">ポリシーを選択して、構成と状態の詳細を確認します (たとえば、まだテスト中、テスト完了など)。</span><span class="sxs-lookup"><span data-stu-id="876e3-323">Select your policy to see the details of the configuration and status (for example, still testing or test complete).</span></span> <span data-ttu-id="876e3-324">[**一致したアイテム**] タブを選択して、指定したルールに一致するメールまたはドキュメントを確認します。</span><span class="sxs-lookup"><span data-stu-id="876e3-324">Select the **Matched items** tab to see which emails or documents matched the rules that you specified.</span></span>

<span data-ttu-id="876e3-325">ページの上部にある [**編集**] オプションを選択すると、このインターフェイスから直接ポリシーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="876e3-325">You can modify your policy directly from this interface by selecting the **Edit** option at the top of the page.</span></span>

<span data-ttu-id="876e3-326">シミュレーションなしでポリシーを実行する準備ができたら、[**有効にする**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="876e3-326">When you're ready to run the policy without simulation, select the **Turn On** option.</span></span>

<span data-ttu-id="876e3-327">また、適切な[アクセス許可](data-classification-content-explorer.md#permissions)がある場合は、[コンテンツ エクスプローラー](data-classification-content-explorer.md)を使用して、自動ラベル付けポリシーの結果を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="876e3-327">You can also see the results of your auto-labeling policy by using [content explorer](data-classification-content-explorer.md) when you have the appropriate [permissions](data-classification-content-explorer.md#permissions):</span></span>
- <span data-ttu-id="876e3-328">**コンテンツ エクスプローラー リスト ビューアー**では、ファイルのラベルは表示できますが、ファイルのコンテンツは表示できません。</span><span class="sxs-lookup"><span data-stu-id="876e3-328">**Content Explorer List viewer** lets you see a file's label but not the file's contents.</span></span>
- <span data-ttu-id="876e3-329">**コンテンツ エクスプローラー コンテンツ ビューアー**では、ファイルの内容を表示できます。</span><span class="sxs-lookup"><span data-stu-id="876e3-329">**Content Explorer Content viewer** lets you see the file's contents.</span></span>

> [!TIP]
> <span data-ttu-id="876e3-330">コンテンツ エクスプローラーを使用して、機密情報を含むラベルの付いていないドキュメントがある場所を特定することもできます。</span><span class="sxs-lookup"><span data-stu-id="876e3-330">You can also use content explorer to identify locations that have unlabeled documents that contain sensitive information.</span></span> <span data-ttu-id="876e3-331">この情報を使用して、自動ラベル付けポリシーにこれらの場所を追加することを検討し、識別された機密情報の種類をルールとして含めます。</span><span class="sxs-lookup"><span data-stu-id="876e3-331">Using this information, consider adding these locations to your auto-labeling policy, and include the identified sensitive information types as rules.</span></span>


