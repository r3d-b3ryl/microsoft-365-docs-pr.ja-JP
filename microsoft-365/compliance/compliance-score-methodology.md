---
title: コンプライアンススコアの計算
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
ms.openlocfilehash: ca8615f8c15264104faa71d155d2656cd788bd53
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078634"
---
# <a name="microsoft-compliance-score-preview-calculation"></a><span data-ttu-id="15682-103">Microsoft コンプライアンススコア (プレビュー) の計算</span><span class="sxs-lookup"><span data-stu-id="15682-103">Microsoft Compliance Score (Preview) calculation</span></span>

> [!IMPORTANT]
> <span data-ttu-id="15682-104">コンプライアンススコアは、特定の標準または規制に対する組織のコンプライアンスの絶対的な測定基準を表しているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="15682-104">Compliance Score does not express an absolute measure of organizational compliance with any particular standard or regulation.</span></span> <span data-ttu-id="15682-105">このことは、個人データや個人のプライバシーに対するリスクを軽減するために、制御を採用した範囲を表しています。</span><span class="sxs-lookup"><span data-stu-id="15682-105">It expresses the extent to which you have adopted controls which can reduce the risks to personal data and individual privacy.</span></span> <span data-ttu-id="15682-106">コンプライアンススコアとコンプライアンスマネージャーからの推奨事項は、コンプライアンスの保証として解釈されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="15682-106">Recommendations from Compliance Score and Compliance Manager should not be interpreted as a guarantee of compliance.</span></span> <span data-ttu-id="15682-107">このサービスは現在プレビュー段階であり、[オンラインサービス](https://go.microsoft.com/fwlink/?linkid=2108910)の使用条件の条件に従います。</span><span class="sxs-lookup"><span data-stu-id="15682-107">This service is currently in preview and is subject to the terms and conditions in the [Online Services Terms](https://go.microsoft.com/fwlink/?linkid=2108910).</span></span>

## <a name="overview"></a><span data-ttu-id="15682-108">概要</span><span class="sxs-lookup"><span data-stu-id="15682-108">Overview</span></span>

<span data-ttu-id="15682-109">コンプライアンススコアダッシュボードには、コントロール内の改善アクションを完了するための進行状況を測定するスコアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="15682-109">The Compliance Score dashboard displays a score that measures your progress in completing improvement actions within controls.</span></span> <span data-ttu-id="15682-110">操作が完了すると、ポイントが計上します。</span><span class="sxs-lookup"><span data-stu-id="15682-110">Your points accrue when you complete actions.</span></span>

<span data-ttu-id="15682-111">スコアは、Microsoft が管理するアクションとお客様が管理するアクションの完了に基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="15682-111">Your score is calculated based on the completion of Microsoft-managed actions and customer-managed actions.</span></span> <span data-ttu-id="15682-112">各アクションは、発生する可能性のあるリスクに応じて、スコアにさまざまな影響を与えます。そのため、スコアは、全体的なコンプライアンスの状況を改善するために、どのアクションに集中するかを優先することができます。</span><span class="sxs-lookup"><span data-stu-id="15682-112">Each action has a different impact on your score, depending on the potential risks involved, so the score can help prioritize which action to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="15682-113">コントロールの表示されるコンプライアンススコアの値は、合格/不合格時の合計スコアに*完全*に適用されます。</span><span class="sxs-lookup"><span data-stu-id="15682-113">The displayed Compliance Score values for the control are applied *in their entirety* to your total score on a pass/fail basis.</span></span> <span data-ttu-id="15682-114">コントロールが実装されていて、以降の評価テストに合格しているかどうか。</span><span class="sxs-lookup"><span data-stu-id="15682-114">Either the control is implemented and passes the subsequent assessment test or it does not.</span></span> <span data-ttu-id="15682-115">割り当てられたポイントは、コントロールが次の場合にコンプライアンススコアに追加されます。</span><span class="sxs-lookup"><span data-stu-id="15682-115">Assigned points are added to Compliance Score when the control has:</span></span>

- <span data-ttu-id="15682-116">**実装の状態**は、**実装**済みまたは**代替の実装**と同じで、</span><span class="sxs-lookup"><span data-stu-id="15682-116">**Implementation Status** equals **Implemented** or **Alternative Implementation** and,</span></span>
- <span data-ttu-id="15682-117">**テスト結果**が**渡さ**れた値に等しい。</span><span class="sxs-lookup"><span data-stu-id="15682-117">**Test Result** equals **Passed**.</span></span>

<span data-ttu-id="15682-118">向上した操作によって獲得したポイントの合計は、コントロールスコアです。</span><span class="sxs-lookup"><span data-stu-id="15682-118">The sum of points earned by taking improvement actions is the control score.</span></span> <span data-ttu-id="15682-119">コントロールスコアの合計は評価スコアです。</span><span class="sxs-lookup"><span data-stu-id="15682-119">The sum of your control scores is the assessment score.</span></span> <span data-ttu-id="15682-120">評価スコアの合計は、全体的なコンプライアンススコアとなります。</span><span class="sxs-lookup"><span data-stu-id="15682-120">The sum of your assessment scores is your overall compliance score</span></span>

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a><span data-ttu-id="15682-121">Microsoft 365 データ保護基準に基づく初期スコア</span><span class="sxs-lookup"><span data-stu-id="15682-121">Initial score based on Microsoft 365 data protection baseline</span></span>
  
<span data-ttu-id="15682-122">コンプライアンススコアには、Microsoft 365 データ保護基準に基づく、すぐに使用できるスコアが用意されています。これは、データ保護と一般的なデータガバナンスの主要な規則と標準が含まれる一連のコントロールです。</span><span class="sxs-lookup"><span data-stu-id="15682-122">Compliance Score gives you an out-of-the-box score based on the Microsoft 365 data protection baseline, which is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span> <span data-ttu-id="15682-123">この基準は、主に NIST CSF (米国規格およびテクノロジ Cybersecurity フレームワーク) および ISO (国際標準化機構)、および FedRAMP (連邦リスクおよび承認管理) からの要素を描画します。プログラム) と GDPR (欧州連合の一般的なデータ保護規則)。</span><span class="sxs-lookup"><span data-stu-id="15682-123">This baseline draws elements primarily from NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) and ISO (International Organization for Standardization), as well as from FedRAMP (Federal Risk and Authorization Management Program) and GDPR (General Data Protection Regulation of the European Union).</span></span>

## <a name="how-compliance-score-continuously-assesses-controls"></a><span data-ttu-id="15682-124">コンプライアンススコアが継続的に制御を評価する方法</span><span class="sxs-lookup"><span data-stu-id="15682-124">How Compliance Score continuously assesses controls</span></span>

<span data-ttu-id="15682-125">コンプライアンススコアは自動的に Microsoft 365 環境をスキャンし、システム設定を検出して、技術的な管理の状態を継続的に、自動的に更新します。</span><span class="sxs-lookup"><span data-stu-id="15682-125">Compliance Score automatically scans through your Microsoft 365 environment and detects your system settings, continuously and automatically updating your technical control status.</span></span> <span data-ttu-id="15682-126">コンプライアンススコアは、監視を実行する基になるエンジンとして、セキュリティで保護されたスコアを使用します。</span><span class="sxs-lookup"><span data-stu-id="15682-126">Compliance Score uses Secure Score as the underlying engine that performs the monitoring.</span></span> <span data-ttu-id="15682-127">[セキュリティで保護されたスコアとそのしくみについて説明](../security/mtp/microsoft-secure-score.md)します。</span><span class="sxs-lookup"><span data-stu-id="15682-127">[Learn more about Secure Score and how it works](../security/mtp/microsoft-secure-score.md).</span></span>

<span data-ttu-id="15682-128">コントロールの状態は、24時間ごとにコンプライアンススコアダッシュボードで更新されます。</span><span class="sxs-lookup"><span data-stu-id="15682-128">Your control status is updated on your Compliance Score dashboard every 24 hours.</span></span> <span data-ttu-id="15682-129">コントロールを実装するための推奨事項に従うと、次の日にコントロールの状態が更新されたことがわかります。</span><span class="sxs-lookup"><span data-stu-id="15682-129">Once you follow a recommendation to implement a control, you will see the control status updated the next day.</span></span>

<span data-ttu-id="15682-130">たとえば、Azure AD ポータルで多要素認証 (MFA) をオンにすると、コンプライアンススコアは設定を検出し、コントロールアクセスソリューションの詳細でその設定を反映します。</span><span class="sxs-lookup"><span data-stu-id="15682-130">For example, if you turn on multi-factor authentication (MFA) in the Azure AD portal, Compliance Score detects the setting and reflects that in the control access solution details.</span></span> <span data-ttu-id="15682-131">それとは逆に、MFA をオンにしていない場合は、推奨される処置としてのコンプライアンススコアフラグが設定されています。</span><span class="sxs-lookup"><span data-stu-id="15682-131">Conversely, if you didn’t turn on MFA, Compliance Score flags that as a recommended action for you to take.</span></span>

<span data-ttu-id="15682-132">パブリックプレビューでは、継続的な評価はコントロールの一部で実行できますが、すべてではありません。</span><span class="sxs-lookup"><span data-stu-id="15682-132">During public preview, continuous assessment is available to a portion of controls, but not all.</span></span>
  
## <a name="control-types-and-points"></a><span data-ttu-id="15682-133">コントロールの種類とポイント</span><span class="sxs-lookup"><span data-stu-id="15682-133">Control types and points</span></span>

<span data-ttu-id="15682-134">コンプライアンススコアは、次の2種類のコントロールを追跡します。これらのコントロールには、全体的なスコアに寄与するポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="15682-134">Compliance Score tracks two types of controls—Microsoft-managed and customer-managed—each of which have points that contribute to your overall score:</span></span>

1. <span data-ttu-id="15682-135">**お客様が管理するポイント**は、組織によって管理される統制に基づいてコンプライアンススコアに寄与します。</span><span class="sxs-lookup"><span data-stu-id="15682-135">**Customer-managed points** contribute to your compliance score based on controls managed by your organization.</span></span>
2. <span data-ttu-id="15682-136">**Microsoft が**管理するポイントは、クラウドサービスプロバイダーとして microsoft が管理する統制に基づいて、コンプライアンススコアに寄与します。</span><span class="sxs-lookup"><span data-stu-id="15682-136">**Microsoft-managed points** contribute to your compliance score based on controls managed by Microsoft as a cloud service provider.</span></span>

<span data-ttu-id="15682-137">以下で説明するように、コントロールには、必須か随意かを基準にしたスコア値、および予防的、検出、または是正のいずれであるかに基づいて、評価値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="15682-137">Controls are assigned a score value based on whether they are mandatory or discretionary, and whether they are preventative, detective, or corrective—as described below.</span></span>

### <a name="mandatory-and-discretionary-controls"></a><span data-ttu-id="15682-138">必須および随意コントロール</span><span class="sxs-lookup"><span data-stu-id="15682-138">Mandatory and discretionary controls</span></span>

 - <span data-ttu-id="15682-139">**必須コントロール**は、意図的でも誤っても使用できないアクションです。</span><span class="sxs-lookup"><span data-stu-id="15682-139">**Mandatory controls** are actions that cannot be bypassed either intentionally or accidentally.</span></span> <span data-ttu-id="15682-140">例としては、パスワードの長さ、複雑さ、および有効期限の要件を設定する、集中管理されたパスワードポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="15682-140">An example is a centrally-managed password policy that sets requirements for password length, complexity, and expiration.</span></span> <span data-ttu-id="15682-141">ユーザーがシステムにアクセスするには、これらの要件に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="15682-141">Users must comply with these requirements to access the system.</span></span>
  
 - <span data-ttu-id="15682-142">**随意制御**は、ポリシーを理解し、それに応じて行動することをユーザーに依存します。</span><span class="sxs-lookup"><span data-stu-id="15682-142">**Discretionary controls** rely upon users to understand policy and act accordingly.</span></span> <span data-ttu-id="15682-143">たとえば、ユーザーが自分のコンピューターを離れるときにロックすることを要求するポリシーは、ユーザーに依存しているため、随意制御です。</span><span class="sxs-lookup"><span data-stu-id="15682-143">For example, a policy requiring users to lock their computer when they leave it is a discretionary control because it relies on the user.</span></span>
  
### <a name="preventative-detective-and-corrective-controls"></a><span data-ttu-id="15682-144">予防、検出、是正の各コントロール</span><span class="sxs-lookup"><span data-stu-id="15682-144">Preventative, detective, and corrective controls</span></span>
  
 - <span data-ttu-id="15682-145">**予防的な統制**は特定のリスクを解決します。</span><span class="sxs-lookup"><span data-stu-id="15682-145">**Preventative controls** address specific risks.</span></span> <span data-ttu-id="15682-146">たとえば、暗号化を使用して情報を保護することは、攻撃や侵害に対する予防的な制御です。</span><span class="sxs-lookup"><span data-stu-id="15682-146">For example, protecting information at rest using encryption is a preventative control against attacks and breaches.</span></span> <span data-ttu-id="15682-147">職務の分離は、侵害の競合を管理する予防的な統制であり、不正行為から保護されます。</span><span class="sxs-lookup"><span data-stu-id="15682-147">Separation of duties is a preventative control to manage conflict of interest and guard against fraud.</span></span>
  
 - <span data-ttu-id="15682-148">**検出コントロール**は、異常な状態またはリスクを示すために使用される、または違反が発生したかどうかを判断するために使用できるシステムをアクティブに監視します。</span><span class="sxs-lookup"><span data-stu-id="15682-148">**Detective controls** actively monitor systems to identify irregular conditions or behaviors that represent risk or that can be used to detect intrusions or determine if a breach occurs.</span></span> <span data-ttu-id="15682-149">システムアクセスの監査および特権管理アクションの監査は、検出の監視コントロールの種類です。</span><span class="sxs-lookup"><span data-stu-id="15682-149">System access auditing and privileged administrative actions auditing are types of detective monitoring controls.</span></span> <span data-ttu-id="15682-150">コンプライアンス監査は、プロセスの問題を検出するために使用される検出コントロールの1種類です。</span><span class="sxs-lookup"><span data-stu-id="15682-150">Regulatory compliance audits are a type of detective control used to find process issues.</span></span>
  
- <span data-ttu-id="15682-151">**修正コントロール**は、セキュリティインシデントの悪影響を最小限に抑え、是正措置を行って直ちに影響を軽減し、可能であれば損害を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="15682-151">**Corrective controls** try to keep the adverse effects of a security incident to a minimum, take corrective action to reduce the immediate effect, and reverse the damage if possible.</span></span> <span data-ttu-id="15682-152">プライバシーインシデント対応は、違反が発生した後にシステムを運用状態にして復元するための是正的な制御です。</span><span class="sxs-lookup"><span data-stu-id="15682-152">Privacy incident response is a corrective control to limit damage and restore systems to an operational state after a breach.</span></span>
  
<span data-ttu-id="15682-153">各コントロールには、次のリスクに基づいてコンプライアンススコアの値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="15682-153">Each control has an assigned value in Compliance Score based on the risk it represents:</span></span>

|<span data-ttu-id="15682-154">**種類**</span><span class="sxs-lookup"><span data-stu-id="15682-154">**Type**</span></span>|<span data-ttu-id="15682-155">**割り当てられたスコア**</span><span class="sxs-lookup"><span data-stu-id="15682-155">**Assigned score**</span></span>|
|:-----|:-----|
| <span data-ttu-id="15682-156">予防必須</span><span class="sxs-lookup"><span data-stu-id="15682-156">Preventative mandatory</span></span> | <span data-ttu-id="15682-157">27</span><span class="sxs-lookup"><span data-stu-id="15682-157">27</span></span> |
| <span data-ttu-id="15682-158">予防的裁量</span><span class="sxs-lookup"><span data-stu-id="15682-158">Preventative discretionary</span></span> | <span data-ttu-id="15682-159">9 </span><span class="sxs-lookup"><span data-stu-id="15682-159">9</span></span> |
| <span data-ttu-id="15682-160">検出必須</span><span class="sxs-lookup"><span data-stu-id="15682-160">Detective mandatory</span></span> | <span data-ttu-id="15682-161">1/3</span><span class="sxs-lookup"><span data-stu-id="15682-161">3</span></span> |
| <span data-ttu-id="15682-162">検出随意</span><span class="sxs-lookup"><span data-stu-id="15682-162">Detective discretionary</span></span> | <span data-ttu-id="15682-163">1-d</span><span class="sxs-lookup"><span data-stu-id="15682-163">1</span></span> |
| <span data-ttu-id="15682-164">修正必須</span><span class="sxs-lookup"><span data-stu-id="15682-164">Corrective mandatory</span></span> | <span data-ttu-id="15682-165">1/3</span><span class="sxs-lookup"><span data-stu-id="15682-165">3</span></span> |
| <span data-ttu-id="15682-166">随意随意</span><span class="sxs-lookup"><span data-stu-id="15682-166">Corrective discretionary</span></span> | <span data-ttu-id="15682-167">1-d</span><span class="sxs-lookup"><span data-stu-id="15682-167">1</span></span> |
  
