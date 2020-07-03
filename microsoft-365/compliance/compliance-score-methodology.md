---
title: Microsoft コンプライアンススコア (プレビュー) の計算
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: リスクに対処し、コンプライアンスの姿勢を改善するために行われた処置に基づいて、Microsoft コンプライアンススコアが個人のスコアを計算する方法について理解します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69b631dc355ff497d0f6042e0cce6aff3d70e557
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024677"
---
# <a name="compliance-score-preview-calculation"></a><span data-ttu-id="4f964-103">コンプライアンススコア (プレビュー) の計算</span><span class="sxs-lookup"><span data-stu-id="4f964-103">Compliance Score (preview) calculation</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f964-104">コンプライアンス スコアおよびコンプライアンス マネージャーからの推奨事項は、コンプライアンスの保証として解釈してはいけません。</span><span class="sxs-lookup"><span data-stu-id="4f964-104">Recommendations from Compliance Score and Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="4f964-105">お客様は、お客様の規制環境に応じて、カスタマーコントロールの有効性を評価および検証することができます。</span><span class="sxs-lookup"><span data-stu-id="4f964-105">It is up to you to evaluate and validate the effectiveness of customer controls per your regulatory environment.</span></span> <span data-ttu-id="4f964-106">これらのサービスは現在プレビュー段階であり、[オンラインサービス](https://go.microsoft.com/fwlink/?linkid=2108910)の使用条件に従っています。</span><span class="sxs-lookup"><span data-stu-id="4f964-106">These services are currently in preview and subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span> <span data-ttu-id="4f964-107">[セキュリティとコンプライアンスのための Microsoft 365 ライセンスガイダンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)も参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f964-107">See also [Microsoft 365 licensing guidance for security and compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

## <a name="how-compliance-score-works"></a><span data-ttu-id="4f964-108">コンプライアンススコアのしくみ</span><span class="sxs-lookup"><span data-stu-id="4f964-108">How Compliance Score works</span></span>

<span data-ttu-id="4f964-109">コンプライアンススコアダッシュボードには、コントロール内の改善アクションを完了するための進行状況を測定するスコアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f964-109">The Compliance Score dashboard displays a score that measures your progress in completing improvement actions within controls.</span></span> <span data-ttu-id="4f964-110">各アクションは、発生する可能性のあるリスクに応じて、スコアにさまざまな影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="4f964-110">Each action has a different impact on your score, depending on the potential risks involved.</span></span> <span data-ttu-id="4f964-111">スコアは、全体的なコンプライアンス姿勢を改善するために、どのアクションに焦点を当てるかを優先することができます。</span><span class="sxs-lookup"><span data-stu-id="4f964-111">Your score can help prioritize which action to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="4f964-112">コントロールの表示されるコンプライアンススコアの値は、合格/不合格時の合計スコアに*完全*に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4f964-112">The displayed Compliance Score values for the control are applied *in their entirety* to your total score on a pass/fail basis.</span></span> <span data-ttu-id="4f964-113">コントロールが実装されていて、以降の評価テストに合格しているかどうか。</span><span class="sxs-lookup"><span data-stu-id="4f964-113">Either the control is implemented and passes the subsequent assessment test, or it doesn't.</span></span> 

<span data-ttu-id="4f964-114">コントロールが次の場合に、コンプライアンススコアにポイントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="4f964-114">Points are added to your compliance score when the control has:</span></span>

- <span data-ttu-id="4f964-115">**実装の状態**は **、実装済みまたは**代替の**実装**と同じであり、</span><span class="sxs-lookup"><span data-stu-id="4f964-115">**Implementation Status** equals **Implemented** or **Alternative Implementation**, and</span></span>
- <span data-ttu-id="4f964-116">**テスト結果**が**渡さ**れた値に等しい。</span><span class="sxs-lookup"><span data-stu-id="4f964-116">**Test Result** equals **Passed**.</span></span>

<span data-ttu-id="4f964-117">コントロールスコアは、改善アクションを実行することによって獲得されたポイントの合計です。</span><span class="sxs-lookup"><span data-stu-id="4f964-117">A control score is the sum of points earned by taking improvement actions.</span></span> <span data-ttu-id="4f964-118">コントロールスコアの合計は評価スコアです。</span><span class="sxs-lookup"><span data-stu-id="4f964-118">The sum of your control scores is the assessment score.</span></span> <span data-ttu-id="4f964-119">**評価スコアの合計は、全体的なコンプライアンススコアとなります。**</span><span class="sxs-lookup"><span data-stu-id="4f964-119">**The sum of your assessment scores is your overall compliance score.**</span></span>

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a><span data-ttu-id="4f964-120">Microsoft 365 データ保護基準に基づく初期スコア</span><span class="sxs-lookup"><span data-stu-id="4f964-120">Initial score based on Microsoft 365 data protection baseline</span></span>
  
<span data-ttu-id="4f964-121">コンプライアンススコアには、Microsoft 365 データ保護基準に基づく初期スコアが与えられます。</span><span class="sxs-lookup"><span data-stu-id="4f964-121">Compliance Score gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="4f964-122">このベースラインは、データ保護と一般的なデータガバナンスに関する主要な規制と標準を含む一連のコントロールです。</span><span class="sxs-lookup"><span data-stu-id="4f964-122">This baseline is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span> <span data-ttu-id="4f964-123">この基準は、主に NIST CSF (米国国立標準およびテクノロジ Cybersecurity フレームワーク) および ISO (国際標準化機構)、および、FedRAMP (連邦リスクおよび承認管理プログラム) および GDPR (欧州連合の一般的なデータ保護規則) からの要素を描画します。</span><span class="sxs-lookup"><span data-stu-id="4f964-123">This baseline draws elements primarily from NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) and ISO (International Organization for Standardization), as well as from FedRAMP (Federal Risk and Authorization Management Program) and GDPR (General Data Protection Regulation of the European Union).</span></span>

<span data-ttu-id="4f964-124">(既定ではすべての組織に提供されています) データ保護のベースライン評価を使用して、その他の評価を構成する前に最初のスコアを計算します。</span><span class="sxs-lookup"><span data-stu-id="4f964-124">The data protection baseline assessment (provided by default to all organizations) is used to calculate your initial score before you configure any other assessments.</span></span> <span data-ttu-id="4f964-125">最初の訪問時に、コンプライアンススコアは既に Microsoft 365 ソリューションからの信号を収集しています。</span><span class="sxs-lookup"><span data-stu-id="4f964-125">Upon your first visit, Compliance Score is already collecting signals from your Microsoft 365 solutions.</span></span> <span data-ttu-id="4f964-126">重要なデータ保護の標準および規制について、組織がどのように実行されているかがひとめでわかり、推奨される改善アクションを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4f964-126">You’ll see at a glance how your organization is performing relative to key data protection standards and regulations, and see suggested improvement actions to take.</span></span>

<span data-ttu-id="4f964-127">すべての組織に固有のニーズがあるため、コンプライアンススコアは、独自の評価を設定して管理することによって、リスクを最小限に抑え、軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="4f964-127">Because every organization has specific needs, Compliance Score relies on you to set up and manage your own assessments to help minimize and mitigate risk as comprehensively as possible.</span></span>

## <a name="how-compliance-score-continuously-assesses-controls"></a><span data-ttu-id="4f964-128">コンプライアンススコアが継続的に制御を評価する方法</span><span class="sxs-lookup"><span data-stu-id="4f964-128">How Compliance Score continuously assesses controls</span></span>

<span data-ttu-id="4f964-129">コンプライアンススコアは自動的に Microsoft 365 環境をスキャンし、システム設定を検出して、技術的な管理の状態を継続的に、自動的に更新します。</span><span class="sxs-lookup"><span data-stu-id="4f964-129">Compliance Score automatically scans through your Microsoft 365 environment and detects your system settings, continuously and automatically updating your technical control status.</span></span> <span data-ttu-id="4f964-130">セキュリティで保護されたスコアは、監視を実行する基礎となるエンジンです。</span><span class="sxs-lookup"><span data-stu-id="4f964-130">Secure Score is the underlying engine that performs the monitoring.</span></span>

<span data-ttu-id="4f964-131">コントロールの状態は、24時間ごとにコンプライアンススコアダッシュボードで更新されます。</span><span class="sxs-lookup"><span data-stu-id="4f964-131">Your control status is updated on your Compliance Score dashboard every 24 hours.</span></span> <span data-ttu-id="4f964-132">コントロールを実装するための推奨事項に従うと、次の日にコントロールの状態が更新されたことがわかります。</span><span class="sxs-lookup"><span data-stu-id="4f964-132">Once you follow a recommendation to implement a control, you'll see the control status updated the next day.</span></span>

<span data-ttu-id="4f964-133">たとえば、Azure AD ポータルで多要素認証 (MFA) をオンにすると、コンプライアンススコアは設定を検出し、コントロールアクセスソリューションの詳細でその設定を反映します。</span><span class="sxs-lookup"><span data-stu-id="4f964-133">For example, if you turn on multi-factor authentication (MFA) in the Azure AD portal, Compliance Score detects the setting and reflects that in the control access solution details.</span></span> <span data-ttu-id="4f964-134">それとは逆に、MFA をオンにしていない場合は、推奨される処置としてのコンプライアンススコアフラグが設定されています。</span><span class="sxs-lookup"><span data-stu-id="4f964-134">Conversely, if you didn't turn on MFA, Compliance Score flags that as a recommended action for you to take.</span></span>

<span data-ttu-id="4f964-135">パブリックプレビューでは、継続的な評価はコントロールの一部で実行できますが、すべてではありません。</span><span class="sxs-lookup"><span data-stu-id="4f964-135">During public preview, continuous assessment is available to a portion of controls, but not all.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="4f964-136">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4f964-136">Learn more</span></span>
<span data-ttu-id="4f964-137">[セキュリティで保護されたスコアとそのしくみについて確認](../security/mtp/microsoft-secure-score-new.md)します。</span><span class="sxs-lookup"><span data-stu-id="4f964-137">[Read about Secure Score and how it works](../security/mtp/microsoft-secure-score-new.md).</span></span>
  
## <a name="action-types-and-points"></a><span data-ttu-id="4f964-138">アクションの種類とポイント</span><span class="sxs-lookup"><span data-stu-id="4f964-138">Action types and points</span></span>

<span data-ttu-id="4f964-139">コンプライアンススコアは、管理するアクションと Microsoft が管理するアクションという2種類のアクションを追跡します。</span><span class="sxs-lookup"><span data-stu-id="4f964-139">Compliance Score tracks two types of actions: actions you manage, and actions Microsoft manages.</span></span> <span data-ttu-id="4f964-140">両方の種類のアクションには、完了時に全体的なスコアにカウントされるポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="4f964-140">Both types of actions have points that count toward your overall score when completed:</span></span>

1. <span data-ttu-id="4f964-141">お客様の**ポイント**は、組織によって管理される統制に基づいてコンプライアンススコアに寄与します。</span><span class="sxs-lookup"><span data-stu-id="4f964-141">**Your points** contribute to your compliance score based on controls managed by your organization.</span></span>
2. <span data-ttu-id="4f964-142">**Microsoft マネージドポイント**は、microsoft がクラウドサービスプロバイダーとして管理するアクションに基づいてコンプライアンススコアに貢献します。</span><span class="sxs-lookup"><span data-stu-id="4f964-142">**Microsoft managed points** contribute to your compliance score based on actions managed by Microsoft as a cloud service provider.</span></span>

<span data-ttu-id="4f964-143">アクションには、必須か随意かを基準にしたスコア値、および予防的、検出、または修正のいずれであるかに基づいて割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="4f964-143">Actions are assigned a score value based on whether they're mandatory or discretionary, and whether they're preventative, detective, or corrective.</span></span>

### <a name="mandatory-and-discretionary-actions"></a><span data-ttu-id="4f964-144">必須および任意のアクション</span><span class="sxs-lookup"><span data-stu-id="4f964-144">Mandatory and discretionary actions</span></span>

 - <span data-ttu-id="4f964-145">**強制アクション**は、意図的でも誤っても、省略することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f964-145">**Mandatory actions** can't be bypassed, either intentionally or accidentally.</span></span> <span data-ttu-id="4f964-146">例としては、パスワードの長さ、複雑さ、および有効期限の要件を設定する、集中管理されたパスワードポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="4f964-146">An example is a centrally managed password policy that sets requirements for password length, complexity, and expiration.</span></span> <span data-ttu-id="4f964-147">ユーザーは、システムにアクセスするためにこれらの要件に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f964-147">Users must follow these requirements to access the system.</span></span>
  
 - <span data-ttu-id="4f964-148">**随意アクション**は、ポリシーを理解し、それに応じて行動することに依存します。</span><span class="sxs-lookup"><span data-stu-id="4f964-148">**Discretionary actions** rely upon users to understand policy and act accordingly.</span></span> <span data-ttu-id="4f964-149">たとえば、ユーザーが自分のコンピューターを離れるときにロックすることを要求するポリシーは、ユーザーに依存しているため、随意操作です。</span><span class="sxs-lookup"><span data-stu-id="4f964-149">For example, a policy requiring users to lock their computer when they leave it is a discretionary action because it relies on the user.</span></span>
  
### <a name="preventative-detective-and-corrective-actions"></a><span data-ttu-id="4f964-150">予防的、検出、および是正処置</span><span class="sxs-lookup"><span data-stu-id="4f964-150">Preventative, detective, and corrective actions</span></span>
  
 - <span data-ttu-id="4f964-151">**予防的**措置は特定のリスクに対応します。</span><span class="sxs-lookup"><span data-stu-id="4f964-151">**Preventative actions** address specific risks.</span></span> <span data-ttu-id="4f964-152">たとえば、暗号化を使用して情報を保護することは、攻撃と侵害に対する予防的な処置になります。</span><span class="sxs-lookup"><span data-stu-id="4f964-152">For example, protecting information at rest using encryption is a preventative action against attacks and breaches.</span></span> <span data-ttu-id="4f964-153">職務の分離は、侵害の競合を管理し、不正行為から保護する予防的な処置です。</span><span class="sxs-lookup"><span data-stu-id="4f964-153">Separation of duties is a preventative action to manage conflict of interest and guard against fraud.</span></span>
  
 - <span data-ttu-id="4f964-154">**検出アクション**は、システムを積極的に監視し、リスクを表す、または侵入または違反を検出するために使用できる、変則的な条件や動作を識別します。</span><span class="sxs-lookup"><span data-stu-id="4f964-154">**Detective actions** actively monitor systems to identify irregular conditions or behaviors that represent risk, or that can be used to detect intrusions or breaches.</span></span> <span data-ttu-id="4f964-155">例としては、システムアクセスの監査と特権管理の操作があります。</span><span class="sxs-lookup"><span data-stu-id="4f964-155">Examples include system access auditing and privileged administrative actions.</span></span> <span data-ttu-id="4f964-156">コンプライアンス監査は、プロセスの問題を検出するために使用される検出アクションの一種です。</span><span class="sxs-lookup"><span data-stu-id="4f964-156">Regulatory compliance audits are a type of detective action used to find process issues.</span></span>
  
- <span data-ttu-id="4f964-157">**是正**措置は、セキュリティインシデントの悪影響を最小限に抑え、是正措置を行って直ちに影響を軽減し、可能であれば損害を元に戻すようにしてください。</span><span class="sxs-lookup"><span data-stu-id="4f964-157">**Corrective actions** try to keep the adverse effects of a security incident to a minimum, take corrective action to reduce the immediate effect, and reverse the damage if possible.</span></span> <span data-ttu-id="4f964-158">プライバシーインシデント対応は、違反を制限し、システムを侵害した後、運用状態に復元するための是正措置です。</span><span class="sxs-lookup"><span data-stu-id="4f964-158">Privacy incident response is a corrective action to limit damage and restore systems to an operational state after a breach.</span></span>
  
<span data-ttu-id="4f964-159">各アクションは、それが表すリスクに基づいて、コンプライアンススコアに割り当てられた値を持ちます。</span><span class="sxs-lookup"><span data-stu-id="4f964-159">Each action has an assigned value in Compliance Score based on the risk it represents:</span></span>

|<span data-ttu-id="4f964-160">**型**</span><span class="sxs-lookup"><span data-stu-id="4f964-160">**Type**</span></span>|<span data-ttu-id="4f964-161">**割り当てられたスコア**</span><span class="sxs-lookup"><span data-stu-id="4f964-161">**Assigned score**</span></span>|
|:-----|:-----|
| <span data-ttu-id="4f964-162">予防必須</span><span class="sxs-lookup"><span data-stu-id="4f964-162">Preventative mandatory</span></span> | <span data-ttu-id="4f964-163">27</span><span class="sxs-lookup"><span data-stu-id="4f964-163">27</span></span> |
| <span data-ttu-id="4f964-164">予防的裁量</span><span class="sxs-lookup"><span data-stu-id="4f964-164">Preventative discretionary</span></span> | <span data-ttu-id="4f964-165">9 </span><span class="sxs-lookup"><span data-stu-id="4f964-165">9</span></span> |
| <span data-ttu-id="4f964-166">検出必須</span><span class="sxs-lookup"><span data-stu-id="4f964-166">Detective mandatory</span></span> | <span data-ttu-id="4f964-167">3 </span><span class="sxs-lookup"><span data-stu-id="4f964-167">3</span></span> |
| <span data-ttu-id="4f964-168">検出随意</span><span class="sxs-lookup"><span data-stu-id="4f964-168">Detective discretionary</span></span> | <span data-ttu-id="4f964-169">1 </span><span class="sxs-lookup"><span data-stu-id="4f964-169">1</span></span> |
| <span data-ttu-id="4f964-170">修正必須</span><span class="sxs-lookup"><span data-stu-id="4f964-170">Corrective mandatory</span></span> | <span data-ttu-id="4f964-171">3 </span><span class="sxs-lookup"><span data-stu-id="4f964-171">3</span></span> |
| <span data-ttu-id="4f964-172">随意随意</span><span class="sxs-lookup"><span data-stu-id="4f964-172">Corrective discretionary</span></span> | <span data-ttu-id="4f964-173">1 </span><span class="sxs-lookup"><span data-stu-id="4f964-173">1</span></span> |
  
<span data-ttu-id="4f964-174">![コンプライアンススコアコントロールのポイント値](../media/compliance-score-controls-scoring.png "コンプライアンススコアコントロールのポイント値")</span><span class="sxs-lookup"><span data-stu-id="4f964-174">![Compliance Score controls point values](../media/compliance-score-controls-scoring.png "Compliance Score controls point values")</span></span>