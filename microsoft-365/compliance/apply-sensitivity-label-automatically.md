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
ms.openlocfilehash: a1ea81bf8c65d3f54d26b19eae3b590f11283c30
ms.sourcegitcommit: 109b44aa71bb8453d0a602663df0fcf7ed7dfdbe
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2020
ms.locfileid: "42277214"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="7fd3e-103">機密ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="7fd3e-103">Apply a sensitivity label to content automatically</span></span>

<span data-ttu-id="7fd3e-104">機密ラベルを作成する場合、機密情報が含まれている場合にそのラベルをコンテンツに自動的に割り当てるか、あるいは推奨するラベルを適用するようにユーザーに求めることができます。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-104">When you create a sensitivity label, you can automatically assign that label to content when it contains sensitive information, or you can prompt users to apply the label that you recommend.</span></span>

<span data-ttu-id="7fd3e-105">機密ラベルを自動的にコンテンツに適用する機能が重要である理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-105">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="7fd3e-106">ユーザーのトレーニングは、一部の分類方法についてのみ必要。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-106">You don't need to train your users on all of your classifications.</span></span>

- <span data-ttu-id="7fd3e-107">ユーザーへの依存は、一部のコンテンツを正しく分類するためにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-107">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="7fd3e-108">ユーザーはポリシーについて把握する必要がなくなり、自分たちの仕事に集中できます。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-108">Users no longer need to know about your policies — they can instead focus on their work.</span></span>

<span data-ttu-id="7fd3e-109">Windows 用 Office アプリの自動ラベル付けは、Azure Information Protection 統合ラベル付けクライアントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-109">Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="7fd3e-110">Office アプリ組み込みのラベル付けでは、この機能が[一部のアプリでプレビュー](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)されています。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-110">For built-in labeling in Office apps, this capability is [in preview for some apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

<span data-ttu-id="7fd3e-111">Office アプリの自動ラベル付け設定は、[機密ラベルを作成または編集する](create-sensitivity-labels.md)ときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-111">The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md):</span></span>

![機密ラベルの自動ラベル付けオプション](../media/sensitivity-labels-auto-labeling-options.png)

## <a name="how-to-configure-auto-labeling-for-office-apps"></a><span data-ttu-id="7fd3e-113">Office アプリの自動ラベル付けを構成する方法</span><span class="sxs-lookup"><span data-stu-id="7fd3e-113">How to configure auto-labeling for Office apps</span></span>

<span data-ttu-id="7fd3e-114">機密ラベルの最も強力な機能の 1 つは、特定の条件に一致したコンテンツに自動的に機密ラベルを適用する能力です。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-114">One of the most powerful features of sensitivity labels is the ability to apply them automatically to content that matches certain conditions.</span></span> <span data-ttu-id="7fd3e-115">この場合、組織内のユーザーが機密ラベルを適用する必要はありません。これは Office 365 により自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-115">In this case, people in your organization don't need to apply the sensitivity labels — Office 365 does the work for them.</span></span>

<span data-ttu-id="7fd3e-116">コンテンツに特定の種類の機密情報が含まれている場合、機密ラベルをコンテンツに自動的に適用することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-116">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information.</span></span> <span data-ttu-id="7fd3e-117">機密情報の種類または分類子のリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-117">Choose from a list of sensitive info types or classifers:</span></span>

![Office アプリの自動ラベル付けのラベル条件](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> <span data-ttu-id="7fd3e-119">現在、**分類子** のオプションは制限付きプレビュー中であり、テナントでこの機能を有効にするには Microsoft にフォームを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-119">Currently, the option for **Classifers** is in limited preview and requires you to submit a form to Microsoft to enable this capability for your tenant.</span></span> <span data-ttu-id="7fd3e-120">詳細については、「[Announcing automatic labeling in Office Apps using built-in classifiers - Limited Preview (組み込みの分類子を使用した Office アプリの自動ラベル付けの発表 - 制限付きプレビュー)](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889)」のブログ投稿を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-120">For more information, see the blog post [Announcing automatic labeling in Office Apps using built-in classifiers - Limited Preview](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span></span>

<span data-ttu-id="7fd3e-121">この機密ラベルが自動的に適用されると、ユーザーの Office アプリに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-121">When this sensitivity label is automatically applied, the user sees a notification in their Office app.</span></span> <span data-ttu-id="7fd3e-122">[**OK**] をクリックして通知を閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-122">They can choose **OK** to dismiss the notification.</span></span>

![ドキュメントにラベルが自動適用されたという通知](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a><span data-ttu-id="7fd3e-124">ラベルの機密情報の種類の構成</span><span class="sxs-lookup"><span data-stu-id="7fd3e-124">Configuring sensitive info types for a label</span></span>

<span data-ttu-id="7fd3e-125">**機密情報の種類** オプションを選択すると、データ損失防止 (DLP) ポリシーを作成するときと同じ機密情報の種類の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-125">When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="7fd3e-126">そのため、たとえば、クレジットカード番号や社会保障番号など、お客様の個人情報 (PII) を含むコンテンツに極秘ラベルを自動的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-126">So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers:</span></span>

![Officeアプリの自動ラベル付け用の機密情報の種類](../media/sensitivity-labels-sensitive-info-types.png)

<span data-ttu-id="7fd3e-128">機密情報の種類を選択した後は、インスタンス数または一致精度を変更して条件を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-128">After you select your sensitive information types, you can refine your condition by changing the instance count or match accuracy.</span></span> <span data-ttu-id="7fd3e-129">詳細については、「[一致の難易度を設定するためのルールの調整](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-129">For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="7fd3e-130">さらに、条件で検知する必要があるのは、機密情報の種類のすべてか、またはそのうちの 1 つだけかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-130">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="7fd3e-131">また、条件をより柔軟または複雑にするには、グループを追加し、グループ間で論理演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-131">And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups.</span></span> <span data-ttu-id="7fd3e-132">詳細については、「[グループ化および論理演算子](data-loss-prevention-policies.md#grouping-and-logical-operators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-132">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

![インスタンス数と一致精度のオプション](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifers-for-a-label"></a><span data-ttu-id="7fd3e-134">ラベルの分類子の構成</span><span class="sxs-lookup"><span data-stu-id="7fd3e-134">Configuring classifers for a label</span></span>

<span data-ttu-id="7fd3e-135">**分類子** オプションを選択する場合、1 つ以上の組み込み分類子を選択します。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-135">When you select the **Classifers** option, select one or more of the built-in classifiers:</span></span>

![分類子と機密ラベルのオプション](../media/sensitivity-labels-classifers.png)

<span data-ttu-id="7fd3e-137">それらの分類子の詳細については、「[トレーニング可能な分類子 (プレビュー) の概要](classifier-getting-started-with.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-137">For more information about these classifers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="7fd3e-138">プレビュー期間中は、次のアプリが機密ラベルの分類子をサポートします。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-138">During the preview period, the following apps support classifers for sensitivity labels:</span></span>

- <span data-ttu-id="7fd3e-139">[Office Insider](https://office.com/insider) の Windows 用 Office 365 ProPlus デスクトップ アプリ:</span><span class="sxs-lookup"><span data-stu-id="7fd3e-139">Office 365 ProPlus desktop apps for Windows, from [Office Insider](https://office.com/insider):</span></span>
    - <span data-ttu-id="7fd3e-140">Word</span><span class="sxs-lookup"><span data-stu-id="7fd3e-140">Word</span></span>
    - <span data-ttu-id="7fd3e-141">Excel</span><span class="sxs-lookup"><span data-stu-id="7fd3e-141">Excel</span></span>
    - <span data-ttu-id="7fd3e-142">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7fd3e-142">PowerPoint</span></span>

- <span data-ttu-id="7fd3e-143">[SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にする機能 (パブリック プレビュー)](sensitivity-labels-sharepoint-onedrive-files.md) が有効になっている場合の Web アプリ用の Office:</span><span class="sxs-lookup"><span data-stu-id="7fd3e-143">Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    - <span data-ttu-id="7fd3e-144">Word</span><span class="sxs-lookup"><span data-stu-id="7fd3e-144">Word</span></span>
    - <span data-ttu-id="7fd3e-145">Excel</span><span class="sxs-lookup"><span data-stu-id="7fd3e-145">Excel</span></span>
    - <span data-ttu-id="7fd3e-146">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7fd3e-146">PowerPoint</span></span>
    - <span data-ttu-id="7fd3e-147">Outlook</span><span class="sxs-lookup"><span data-stu-id="7fd3e-147">Outlook</span></span>

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a><span data-ttu-id="7fd3e-148">ユーザーが機密ラベルを適用することを推奨</span><span class="sxs-lookup"><span data-stu-id="7fd3e-148">Recommend that the user apply a sensitivity label</span></span>

<span data-ttu-id="7fd3e-149">状況に応じて、ユーザーがラベルを適用することを推奨できます。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-149">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="7fd3e-150">このオプションでは、分類および関連する保護を受け入れるか、またはラベルがそのコンテンツに適していない場合、推奨事項を無視するかをユーザーが選択できます。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-150">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.</span></span>

<span data-ttu-id="7fd3e-151">推奨ラベルは、Word、PowerPoint、および Excel でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-151">Recommended labels are supported for Word, PowerPoint, and Excel.</span></span>

![機密ラベルをユーザーに推奨するためのオプション](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="7fd3e-p110">ラベルを推奨される操作として適用するように条件を構成したときのプロンプトの例を、カスタム ポリシー ヒントと共に示します。ポリシー ヒントに表示するテキストを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-p110">Here's an example of a prompt when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.</span></span>

![推奨ラベルを適用するためのプロンプト](../media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="7fd3e-156">自動ラベルと推奨ラベルが適用されるしくみ</span><span class="sxs-lookup"><span data-stu-id="7fd3e-156">How automatic or recommended labels are applied</span></span>

- <span data-ttu-id="7fd3e-157">自動ラベル付けは、Word、Excel、PowerPoint でドキュメントが保存されるときと、Outlook で電子メールが送信されるときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-157">Automatic labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span> <span data-ttu-id="7fd3e-158">これらの条件により、ドキュメントや電子メール内の本文、およびヘッダーとフッターに含まれる機密情報が検出されますが、件名や電子メールの添付ファイルのものは検知されません。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-158">These conditions detect sensitive information in the body text in documents and emails, and to headers and footers — but not in the subject line or attachments of email.</span></span>

- <span data-ttu-id="7fd3e-159">以前に手動でラベルが付けられているか、以前に上位の機密度で自動的にラベルが付けられているドキュメントと電子メールには自動ラベル付けを使用できません。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-159">You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity.</span></span> <span data-ttu-id="7fd3e-160">ドキュメントや電子メールに適用できる機密ラベルは (1 つの保持ラベルに加えて) 1 つだけであることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-160">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="7fd3e-161">推奨ラベル付けは、Word、Excel、PowerPoint でドキュメントが保存されるときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-161">Recommended labeling applies to Word, Excel, and PowerPoint when you save documents.</span></span>

- <span data-ttu-id="7fd3e-162">以前に上位の機密度でラベルが付けられているドキュメントには推奨ラベル付けを使用できません。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-162">You can't use recommended labeling for documents that were previously labeled with a higher sensitivity.</span></span> <span data-ttu-id="7fd3e-163">コンテンツにすでに上位の機密度でラベルが付けられている場合、推奨事項とポリシー ヒントに関するプロンプトは、ユーザーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-163">When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="7fd3e-164">複数のラベルに適用するときの複数の条件の評価方法</span><span class="sxs-lookup"><span data-stu-id="7fd3e-164">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="7fd3e-p114">ラベルは、ポリシー内で指定した位置に従って評価の順序を決められます。先頭に配置したラベルが最下位 (機密性が最も低い) になり、最後に配置したラベルが最上位 (機密性が最も高い) になります。優先度に関する詳細については、「[ラベルの優先度 (順序の問題)](sensitivity-labels.md#label-priority-order-matters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-p114">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="7fd3e-167">自動適用または推奨されるように親ラベルを構成しない</span><span class="sxs-lookup"><span data-stu-id="7fd3e-167">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="7fd3e-168">親ラベル (サブラベルのあるラベル) はコンテンツに適用できません。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-168">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="7fd3e-169">親ラベルは Azure Information Protection 統合ラベル付けクライアントを使用する Office アプリのコンテンツには適用されないため、決して親ラベルを自動適用または推奨するように構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-169">Make sure that you don't configure a parent label to be auto-applied or recommended, because the parent label won't be applied to content in Office apps that use the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="7fd3e-170">親ラベルとサブラベルの詳細については、「[サブラベル (ラベルのグループ化)](sensitivity-labels.md#sublabels-grouping-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fd3e-170">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>
