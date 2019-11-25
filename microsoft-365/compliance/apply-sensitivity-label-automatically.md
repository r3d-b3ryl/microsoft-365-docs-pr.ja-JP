---
title: 機密ラベルをコンテンツに自動的に適用する
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: 11/01/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: 機密ラベルを作成する場合、ドキュメントまたは電子メールにラベルを自動的に割り当てるか、あるいは推奨するラベルを選択するようにユーザーに求めることができます。
ms.openlocfilehash: eccc60dc7a306f3e7b2eb128ed45a92af65491a5
ms.sourcegitcommit: cd748ca00088275372f51fbf8c4bc72bfd3e1437
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2019
ms.locfileid: "39233227"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="3a1d2-103">機密ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="3a1d2-103">Apply a sensitivity label to content automatically</span></span>

<span data-ttu-id="3a1d2-104">機密ラベルを作成する場合、機密情報を含むコンテンツにそのラベルを自動的に割り当てるか、あるいは推奨するラベルを適用するようにユーザーに求めることができます。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-104">When you create a sensitivity label, you can automatically assign that label to content containing sensitive information, or you can prompt users to apply the label that you recommend.</span></span>

<span data-ttu-id="3a1d2-105">機密ラベルを自動的にコンテンツに適用する機能が重要である理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-105">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="3a1d2-106">ユーザーのトレーニングは、一部の分類方法についてのみ必要。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-106">You don't need to train your users on all of your classifications.</span></span>

- <span data-ttu-id="3a1d2-107">ユーザーへの依存は、一部のコンテンツを正しく分類するためにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-107">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="3a1d2-108">ユーザーはポリシーについて把握する必要がなくなり、自分たちの仕事に集中できる。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-108">Users no longer need to know about your policies - they can instead focus on their work.</span></span>

<span data-ttu-id="3a1d2-109">ライセンスの要件の詳細については、「[Office アプリの機密ラベル](sensitivity-labels-office-apps.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-109">For information about license requirements, see [Sensitivity labels in Office apps](sensitivity-labels-office-apps.md).</span></span>

<span data-ttu-id="3a1d2-110">自動ラベル付けの設定は、Microsoft 365 コンプライアンス センター、Microsoft 365 セキュリティ センター、Office 365 セキュリティ/コンプライアンス センターの **[分類]**  >  **[機密ラベル]** で機密ラベルを作成するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-110">The auto-labeling settings are available when you create a sensitivity label in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center under **Classification** > **Sensitivity labels**.</span></span>

![機密ラベルの自動ラベル付けオプション](media/Sensitivity-labels-Auto-labeling-options.png)

## <a name="apply-a-sensitivity-label-automatically-based-on-conditions"></a><span data-ttu-id="3a1d2-112">条件に基づいた機密ラベルの自動適用</span><span class="sxs-lookup"><span data-stu-id="3a1d2-112">Apply a sensitivity label automatically based on conditions</span></span>

<span data-ttu-id="3a1d2-113">機密ラベルの最も強力な機能の 1 つは、特定の条件に一致したコンテンツに自動的に機密ラベルを適用する能力です。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-113">One of the most powerful features of sensitivity labels is the ability to apply them automatically to content that matches certain conditions. In this case, people in your organization don't need to apply the sensitivity labels - Office 365 does the work for them.</span></span> <span data-ttu-id="3a1d2-114">この場合、組織内のユーザーが機密ラベルを適用する必要はありません。これは Office 365 により自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-114">One of the most powerful features of sensitivity labels is the ability to apply them automatically to content that matches certain conditions. In this case, people in your organization don't need to apply the sensitivity labels - Office 365 does the work for them.</span></span>

<span data-ttu-id="3a1d2-p102">コンテンツに特定の種類の機密情報が含まれている場合、そのコンテンツに機密ラベルを自動的に適用することを選択できます。機密ラベルを自動的に適用するように構成すると、データ損失防止 (DLP) ポリシーを作成する場合と同じ機密情報の種類のリストが表示されます。たとえば、クレジット カード番号や社会保障番号などの顧客の個人情報 (PII) が含まれるすべてのコンテンツに高機密ラベルを自動的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-p102">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information. When you configure a sensitivity label to be applied automatically, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy. So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers.</span></span>

![インスタンス数と一致精度のオプション](media/Sensitivity-labels-instance-count-match-accuracy.png)

<span data-ttu-id="3a1d2-119">機密情報の種類を選択した後は、インスタンス数または一致精度を変更して条件を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-119">After you choose your sensitive informaton types, you can refine your condition by changing the instance count or match accuracy. For more information, see Tuning rules to make them easier or harder to match.</span></span> <span data-ttu-id="3a1d2-120">詳細については、「[一致の難易度を設定するためのルールの調整](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-120">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="3a1d2-121">さらに、条件で検知する必要があるのは、機密情報の種類のすべてか、またはそのうちの 1 つだけかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-121">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="3a1d2-122">また、条件をより柔軟または複雑にするには、グループを追加し、グループ間で論理演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-122">Further, you can choose whether a condition must detect all of the sensitive infromation types, or just one of them. And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups. For more information, see Grouping and logical operators.</span></span> <span data-ttu-id="3a1d2-123">詳細については、「[グループ化および論理演算子](data-loss-prevention-policies.md#grouping-and-logical-operators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-123">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

<span data-ttu-id="3a1d2-p105">機密ラベルが自動的に適用されると、ユーザーの Office アプリに通知が表示されます。**[OK]** をクリックして通知を閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-p105">When a sensitivity label is automatically applied, the user sees a notification in their Office app. They can choose **OK** to dismiss the notification.</span></span>

![ドキュメントにラベルが自動適用されたという通知](media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a><span data-ttu-id="3a1d2-127">ユーザーが機密ラベルを適用することを推奨</span><span class="sxs-lookup"><span data-stu-id="3a1d2-127">Recommend that the user apply a sensitivity label</span></span>

<span data-ttu-id="3a1d2-128">状況に応じて、ユーザーがラベルを適用することを推奨できます。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-128">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="3a1d2-129">このオプションでは、分類および関連する保護を受け入れるか、またはラベルがドキュメントや電子メールに適していない場合、推奨事項を無視するかをユーザーが選択できます。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-129">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label is not suitable for their document or email.</span></span>

<span data-ttu-id="3a1d2-130">推奨ラベルは、Word、PowerPoint、Excel でサポートされています (Azure Information Protection 統合ラベル付けクライアントがインストールされている必要がります)。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-130">Note that recommended labels are supported in Word, PowerPoint, and Excel (and require that the Azure Information Protection unified labeling client is installed). We're working on support for recommended labels in Outlook.</span></span>

![機密ラベルをユーザーに推奨するためのオプション](media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="3a1d2-p107">ラベルを推奨される操作として適用するように条件を構成したときのプロンプトの例を、カスタム ポリシー ヒントと共に示します。ポリシー ヒントに表示するテキストを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-p107">Here's an example of a prompt when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.</span></span>

![推奨ラベルを適用するためのプロンプト](media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="3a1d2-135">自動ラベルと推奨ラベルが適用されるしくみ</span><span class="sxs-lookup"><span data-stu-id="3a1d2-135">How automatic or recommended labels are applied</span></span>

- <span data-ttu-id="3a1d2-136">自動ラベル付けは、Word、Excel、PowerPoint でドキュメントが保存されるときと、Outlook で電子メールが送信されるときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-136">Automatic labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span> <span data-ttu-id="3a1d2-137">これらの条件により、ドキュメントや電子メール内の本文、およびヘッダーとフッターに含まれる機密情報が検出されますが、件名や電子メールの添付ファイルのものは検知されません。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-137">Automatic labeling applies to Word, Excel, and PowerPoint when documents are saved, and to Outlook when emails are sent. These conditions detect sensitive information in the body text in documents and emails, and to headers and footers -- but not in the subject line or attachments of email.</span></span>

- <span data-ttu-id="3a1d2-138">以前に手動でラベルが付けられているか、以前に上位の分類で自動的にラベルが付けられているドキュメントと電子メールには自動分類を使用できません。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-138">You cannot use automatic classification for documents and emails that were previously manually labeled, or previously automatically labeled with a higher classification. Remember, a document or email can have only a single sensitivity label applied to it (in addition to a single retention label).</span></span> <span data-ttu-id="3a1d2-139">ドキュメントや電子メールに適用できる機密ラベルは (1 つの保持ラベルに加えて) 1 つだけであることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-139">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="3a1d2-140">推奨分類は、Word、Excel、PowerPoint でドキュメントが保存されるときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-140">Recommended classification applies to Word, Excel, and PowerPoint when you save documents.</span></span>

- <span data-ttu-id="3a1d2-141">以前に上位の分類でラベルが付けられているドキュメントには推奨分類を使用できません。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-141">You can't use recommended classification for documents that were previously labeled with a higher classification.</span></span> <span data-ttu-id="3a1d2-142">コンテンツにすでに上位の分類でラベルが付けられている場合、推奨事項とポリシー ヒントに関するプロンプトは、ユーザーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-142">You cannot use recommended classification for documents that were previously labeled with a higher classification. In this case, when the content's already labeled with a higher classification, the user won't see the prompt with the recommendation and policy tip.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="3a1d2-143">複数のラベルに適用するときの複数の条件の評価方法</span><span class="sxs-lookup"><span data-stu-id="3a1d2-143">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="3a1d2-p111">ラベルは、ポリシー内で指定した位置に従って評価の順序を決められます。先頭に配置したラベルが最下位 (機密性が最も低い) になり、最後に配置したラベルが最上位 (機密性が最も高い) になります。優先度に関する詳細については、「[ラベルの優先度 (順序の問題)](sensitivity-labels.md#label-priority-order-matters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-p111">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="3a1d2-146">自動適用または推奨されるように親ラベルを構成しない</span><span class="sxs-lookup"><span data-stu-id="3a1d2-146">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="3a1d2-147">親ラベル (サブラベルのあるラベル) はコンテンツに適用できません。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-147">Remember, a parent label (a label with sublabels) can't be applied to content.</span></span> <span data-ttu-id="3a1d2-148">親ラベルは Azure Information Protection 統合ラベル付けクライアントを使用する Office アプリのコンテンツには適用されないため、決して親ラベルを自動適用または推奨するように構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-148">Make sure that you don't configure a parent label to be auto-applied or recommended, because the parent label won't be applied to content in Office apps that use the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="3a1d2-149">親ラベルとサブラベルの詳細については、「[サブラベル (ラベルのグループ化)](sensitivity-labels.md#sublabels-grouping-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a1d2-149">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>
