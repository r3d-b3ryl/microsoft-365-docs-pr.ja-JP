---
title: Microsoft Defender for microsoft Defender の手順に合った脅威保護Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
ms.reviewer: gigarrub
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
description: Microsoft Defender の脅威フィルター スタックを通じて受信メッセージのパスに従って、Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01ad901f7f746d9b5d2c50632c1344701120c20f
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538689"
---
# <a name="step-by-step-threat-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="bf44f-103">Microsoft Defender for Office 365 でのステップ バイ ステップの脅威に対する保護</span><span class="sxs-lookup"><span data-stu-id="bf44f-103">Step-by-step threat protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="bf44f-104">Microsoft Defender for Office 365保護またはフィルター 処理スタックは、この記事のように 4 つのフェーズに分割できます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-104">The Microsoft Defender for Office 365 protection or filtering stack can be broken out into 4 phases, as in this article.</span></span> <span data-ttu-id="bf44f-105">一般的に、受信メールは配信前にこれらすべてのフェーズを通過しますが、実際のパスは、組織の Defender Office 365 構成の対象になります。</span><span class="sxs-lookup"><span data-stu-id="bf44f-105">Generally speaking, incoming mail passes through all of these phases before delivery, but the actual path email takes is subject to an organization's Defender for Office 365 configuration.</span></span>

> [!TIP]
> <span data-ttu-id="bf44f-106">この記事の最後まで、すべての 4つのフェーズの Defender の統合グラフィックを確認し、Office 365してください。</span><span class="sxs-lookup"><span data-stu-id="bf44f-106">Stay tuned till the end of this article for a *unified* graphic of all 4 phases of Defender for Office 365 protection!</span></span>

## <a name="phase-1---edge-protection"></a><span data-ttu-id="bf44f-107">フェーズ 1 - エッジ保護</span><span class="sxs-lookup"><span data-stu-id="bf44f-107">Phase 1 - Edge Protection</span></span>

<span data-ttu-id="bf44f-108">残念ながら、かつて重要だったエッジブロックは、悪いアクターが克服する場合に比較的簡単になります。</span><span class="sxs-lookup"><span data-stu-id="bf44f-108">Unfortunately, Edge blocks that were once *critical* are now relatively simple for bad actors to overcome.</span></span> <span data-ttu-id="bf44f-109">時間がたつ間に、ここでブロックされるトラフィックは少なくなっていますが、スタックの重要な部分のままです。</span><span class="sxs-lookup"><span data-stu-id="bf44f-109">Over time, less traffic is blocked here, but it remains an important part of the stack.</span></span>  

<span data-ttu-id="bf44f-110">エッジ ブロックは自動的に設計されています。</span><span class="sxs-lookup"><span data-stu-id="bf44f-110">Edge blocks are designed to be automatic.</span></span> <span data-ttu-id="bf44f-111">誤検知の場合、送信者に通知され、問題に対処する方法が通知されます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-111">In the case of false positive, senders will be notified and told how to address their issue.</span></span> <span data-ttu-id="bf44f-112">信頼できるパートナーからの評価が制限されているコネクタは、新しいエンドポイントのオンボーディング時に、配信性を確保したり、一時的な上書きを行う可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bf44f-112">Connectors from trusted partners with limited reputation can ensure deliverability, or temporary overrides can be put in place, when onboarding new endpoints.</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase1.png" alt-text="Defender for Office 365のフェーズ 1 はエッジ保護です。":::

1. <span data-ttu-id="bf44f-114">**ネットワーク調整は** Office 365一連のインフラストラクチャによって送信できるメッセージの数を制限することで、サービス拒否 (DOS) 攻撃からインフラストラクチャと顧客を保護します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-114">**Network throttling** protects Office 365 infrastructure and customers from Denial of Service (DOS) attacks by limiting the number of messages that can be submitted by a specific set of infrastructure.</span></span>

2. <span data-ttu-id="bf44f-115">**IP レピュテーションと調整によって** 、既知の不良接続 IP アドレスから送信されるメッセージがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-115">**IP reputation and throttling** will block messages being sent from known bad connecting IP addresses.</span></span> <span data-ttu-id="bf44f-116">特定の IP が短時間で多数のメッセージを送信すると、そのメッセージは調整されます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-116">If a specific IP sends many messages in a short period of time they will be throttled.</span></span>

3. <span data-ttu-id="bf44f-117">**ドメインレピュ** テーションは、既知の不良ドメインから送信されるメッセージをブロックします。</span><span class="sxs-lookup"><span data-stu-id="bf44f-117">**Domain reputation** will block any messages being sent from a known bad domain.</span></span>

4. <span data-ttu-id="bf44f-118">**ディレクトリ ベースのエッジ フィルター ブロックは** 、SMTP を介して組織のディレクトリ情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-118">**Directory-based edge filtering** blocks attempts to harvest an organization's directory information through SMTP.</span></span>

5. <span data-ttu-id="bf44f-119">**Backscatter 検出により** 、無効な配信不可レポート (NDRs) を通じて組織が攻撃されるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="bf44f-119">**Backscatter detection** prevents an organization from being attacked through invalid non-delivery reports (NDRs).</span></span>

6. <span data-ttu-id="bf44f-120">**コネクタの拡張フィルター処理では、** トラフィックが別のデバイスを通過した場合でも、そのデバイスが別のデバイスに到達する前にOffice 365。</span><span class="sxs-lookup"><span data-stu-id="bf44f-120">**Enhanced filtering for connectors** preserves authentication information even when traffic passes through another device before it reaches Office 365.</span></span> <span data-ttu-id="bf44f-121">これにより、複雑なルーティングシナリオやハイブリッド ルーティング シナリオの場合でも、ヒューリスティック クラスタリング、スプーフィング防止、フィッシング対策機械学習モデルなどのフィルタリング スタックの精度が向上します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-121">This improves filtering stack accuracy, including heuristic clustering, anti-spoofing, and anti-phishing machine learning models, even when in complex or hybrid routing scenarios.</span></span>

## <a name="phase-2---sender-intelligence"></a><span data-ttu-id="bf44f-122">フェーズ 2 - 送信者インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="bf44f-122">Phase 2 - Sender Intelligence</span></span>

<span data-ttu-id="bf44f-123">送信者インテリジェンスの機能は、スパム、バルク、偽装、および不正なスプーフィング メッセージをキャッチし、フィッシング検出を考慮に入れするために重要です。</span><span class="sxs-lookup"><span data-stu-id="bf44f-123">Features in sender intelligence are critical for catching spam, bulk, impersonation, and unauthorized spoof messages, and also factor into phish detection.</span></span> <span data-ttu-id="bf44f-124">これらの機能の大部分は個別に構成できます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-124">Most of these features are individually configurable.</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase2.png" alt-text="MDO でのフィルター処理のフェーズ 2 は、送信者インテリジェンスです。":::

1. <span data-ttu-id="bf44f-126">**アカウントが異常な** 動作を持ち、侵害と一致すると、アカウント侵害検出トリガーとアラートが発生します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-126">**Account compromise detection** triggers and alerts are raised when an account has anomalous behavior, consistent with compromise.</span></span> <span data-ttu-id="bf44f-127">場合によっては、組織のセキュリティ運用チームによって問題が解決されるまで、ユーザー アカウントがブロックされ、それ以上電子メール メッセージを送信できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="bf44f-127">In some cases, the user account is blocked and prevented from sending any further email messages until the issue is resolved by an organization's security operations team.</span></span>

2. <span data-ttu-id="bf44f-128">**電子メール認証** には、クラウドで設定された顧客が構成した方法と方法の両方が含まれるので、送信者が正規の正規のメールを承認することを目的とします。</span><span class="sxs-lookup"><span data-stu-id="bf44f-128">**Email Authentication** involves both customer configured methods and methods set up in the Cloud, aimed at ensuring that senders are authorized, authentic mailers.</span></span> <span data-ttu-id="bf44f-129">これらのメソッドはスプーフィングに抵抗します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-129">These methods resist spoofing.</span></span>
    - <span data-ttu-id="bf44f-130">**SPF** は、組織の代わりにメールを送信できる IP アドレスとサーバーを一覧表示する DNS TXT レコードに基づいてメールを拒否できます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-130">**SPF** can reject mails based on DNS TXT records that list IP addresses and servers allowed to send mail on the organization's behalf.</span></span>
    - <span data-ttu-id="bf44f-131">**DKIM は** 、送信者を認証する暗号化された署名を提供します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-131">**DKIM** provides an encrypted signature that authenticates the sender.</span></span>
    - <span data-ttu-id="bf44f-132">**DMARC を** 使用すると、管理者は SPF と DKIM をドメイン内で必要に応じてマークし、これら 2 つのテクノロジの結果を調整します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-132">**DMARC** lets admins mark SPF and DKIM as required in their domain and enforces alignment between the results of these two technologies.</span></span>
    - <span data-ttu-id="bf44f-133">**ARC** は顧客が構成されていませんが、DMARC 上に構築され、認証チェーンを記録しながら、メール リストの転送を操作します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-133">**ARC** is not customer configured, but builds on DMARC to work with forwarding in mailing lists, while recording an authentication chain.</span></span>

3. <span data-ttu-id="bf44f-134">**ス** プーフィング インテリジェンスは、組織または既知の外部ドメインを模倣する悪意のある送信者から 、スプーフィングを許可されたユーザー (つまり、別のアカウントに代わってメールを送信するユーザー、またはメーリングリストの転送) をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-134">**Spoof intelligence** is capable of filtering those allowed to 'spoof' (that is, those sending mail on behalf of another account, or forwarding for a mailing list) from malicious senders who imitate organizational or known external domains.</span></span> <span data-ttu-id="bf44f-135">これは、スパムやフィッシング メッセージを配信するためにスプーフィングを行う送信者から正当な 「代理」 メールを分離します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-135">It separates legitimate 'on behalf of' mail from senders who spoof to deliver spam and phishing messages.</span></span>

    <span data-ttu-id="bf44f-136">**組織内のスプーフィング インテリジェンスは** 、組織内のドメインからスプーフィングの試行を検出してブロックします。</span><span class="sxs-lookup"><span data-stu-id="bf44f-136">**Intra-org spoof intelligence** detects and blocks spoof attempts from a domain within the organization.</span></span>

4. <span data-ttu-id="bf44f-137">**クロスドメイン スプーフィング インテリジェンスは** 、組織外のドメインからスプーフィングの試行を検出してブロックします。</span><span class="sxs-lookup"><span data-stu-id="bf44f-137">**Cross-domain spoof intelligence** detects and blocks spoof attempts from a domain outside of the organization.</span></span>

5. <span data-ttu-id="bf44f-138">**一括フィルターを** 使用すると、管理者はメッセージが一括送信者から送信されたかどうかを示す一括信頼レベル (BCL) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-138">**Bulk filtering** lets admins configure a bulk confidence level (BCL) indicating whether the message was sent from a bulk sender.</span></span> <span data-ttu-id="bf44f-139">管理者は、スパム対策ポリシーのバルク スライダーを使用して、スパムとして扱うバルク メールのレベルを決定できます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-139">Administrators can use the Bulk Slider in the Antispam policy to decide what level of bulk mail to treat as spam.</span></span>

6. <span data-ttu-id="bf44f-140">**メールボックス インテリジェンスは** 、標準的なユーザーの電子メールの動作から学習します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-140">**Mailbox intelligence** learns from standard user email behaviors.</span></span> <span data-ttu-id="bf44f-141">これは、ユーザーの通信グラフを活用して、送信者がユーザーが通常通信しているが、実際には悪意のあるユーザーにしか見えない場合を検出します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-141">It leverages a user's communication graph to detect when a sender only appears to be someone the user usually communicates with, but is actually malicious.</span></span> <span data-ttu-id="bf44f-142">このメソッドは偽装を検出します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-142">This method detects impersonation.</span></span>

7. <span data-ttu-id="bf44f-143">**メールボックス インテリジェンスの偽装は、** 各ユーザーの個々の送信者マップに基づいて、拡張偽装結果を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="bf44f-143">**Mailbox intelligence impersonation** enables or disables enhanced impersonation results based on each user's individual sender map.</span></span> <span data-ttu-id="bf44f-144">有効にすると、この機能は偽装を識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-144">When enabled, this feature helps to identify impersonation.</span></span>

8. <span data-ttu-id="bf44f-145">**ユーザー偽装を使用** すると、管理者は偽装される可能性が高い値のターゲットのリストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-145">**User impersonation** allows an admin to create a list of high value targets likely to be impersonated.</span></span> <span data-ttu-id="bf44f-146">送信者が保護された高価値アカウントと同じ名前とアドレスを持っているだけのように見えたメールが届いた場合、メールはマークまたはタグ付けされます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-146">If a mail arrives where the sender only appears to have the same name and address as the protected high value account, the mail is marked or tagged.</span></span> <span data-ttu-id="bf44f-147">(たとえば *、trα cye@contoso.com tracye@contoso.com)。*</span><span class="sxs-lookup"><span data-stu-id="bf44f-147">(For example, *trαcye@contoso.com* for *tracye@contoso.com*).</span></span>

9. <span data-ttu-id="bf44f-148">**ドメイン偽装は** 、受信者のドメインに似ていて、内部ドメインのように見えるドメインを検出します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-148">**Domain impersonation** detects domains that are similar to the recipient's domain and that attempt to look like an internal domain.</span></span> <span data-ttu-id="bf44f-149">たとえば、この偽装は、tracye@liw α re.com *に* tracye@litware.com。 </span><span class="sxs-lookup"><span data-stu-id="bf44f-149">For example, this impersonation *tracye@liwαre.com* for *tracye@litware.com*.</span></span>

## <a name="phase-3---content-filtering"></a><span data-ttu-id="bf44f-150">フェーズ 3 - コンテンツ フィルター</span><span class="sxs-lookup"><span data-stu-id="bf44f-150">Phase 3 - Content Filtering</span></span>

<span data-ttu-id="bf44f-151">このフェーズでは、フィルター スタックは、ハイパーリンクや添付ファイルなど、メールの特定のコンテンツの処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-151">In this phase the filtering stack begins to handle the specific contents of the mail, including its hyperlinks and attachments.</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase3.png" alt-text="MDO でのフィルター処理のフェーズ 3 は、コンテンツ フィルターです。":::

1. <span data-ttu-id="bf44f-153">**トランスポート ルール**(メール フロー ルールまたは Exchange トランスポート ルールとも呼ばれる) を使用すると、メッセージに対して同様に幅広い条件が満たされた場合に、管理者は幅広いアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-153">**Transport rules** (also known as mail flow rules or Exchange transport rules) allow an admin to take a wide range of actions when an equally wide range of conditions are met for a message.</span></span> <span data-ttu-id="bf44f-154">組織を流れるすべてのメッセージは、有効なメール フロー ルール/トランスポート ルールに対して評価されます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-154">All messages that flow through your organization are evaluated against the enabled mail flow rules / transport rules.</span></span>

2. <span data-ttu-id="bf44f-155">**Microsoft Defender ウイルス対策** 2 つの *サード パーティ製ウイルス* 対策エンジンを使用して、添付ファイル内のすべての既知のマルウェアを検出します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-155">**Microsoft Defender Antivirus** and two *third-party Antivirus engines* are used to detect all known malware in attachments.</span></span>

3. <span data-ttu-id="bf44f-156">ウイルス対策 (AV) エンジンは、すべての添付ファイルを true 型に設定するためにも使用されます。そのため、タイプ ブロックは管理者が指定した種類のすべての添付ファイルをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-156">The anti-virus (AV) engines are also used to true-type all attachments, so that **Type blocking** can block all attachments of types the admin specifies.</span></span>

4. <span data-ttu-id="bf44f-157">Microsoft Defender for Office 365が悪意のある添付ファイルを検出するたびに、ファイルのハッシュとアクティブ コンテンツのハッシュが Exchange Online Protection (EOP) 評価に追加されます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-157">Whenever Microsoft Defender for Office 365 detects a malicious attachment, the file's hash, and a hash of its active content, are added to Exchange Online Protection (EOP) reputation.</span></span> <span data-ttu-id="bf44f-158">**添付ファイル評価ブロック** は、MSAV クラウド呼び出しをOffice 365、エンドポイント上のすべてのファイルをブロックします。</span><span class="sxs-lookup"><span data-stu-id="bf44f-158">**Attachment reputation blocking** will block that file across all Office 365, and on endpoints, through MSAV cloud calls.</span></span>

5. <span data-ttu-id="bf44f-159">**ヒューリスティック クラスタリングでは** 、ファイルが配信ヒューリスティックに基づいて疑わしいと判断できます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-159">**Heuristic clustering** can determine that a file is suspicious based on delivery heuristics.</span></span> <span data-ttu-id="bf44f-160">疑わしい添付ファイルが見つかると、キャンペーン全体が一時停止し、ファイルがサンドボックス化されます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-160">When a suspicious attachment is found, the entire campaign pauses, and the file is sandboxed.</span></span> <span data-ttu-id="bf44f-161">ファイルが悪意のあるファイルである場合、キャンペーン全体がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-161">If the file is found to be malicious, the entire campaign is blocked.</span></span>

6. <span data-ttu-id="bf44f-162">**機械学習モデルは、** メッセージのヘッダー、本文コンテンツ、URL に基いて、フィッシングの試行を検出します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-162">**Machine learning models** act on the header, body content, and URLs of a message to detect phishing attempts.</span></span>

7. <span data-ttu-id="bf44f-163">Microsoft では、URL サンドボックスからの評価の決定と、URL レピュテーション ブロックのサードパーティ フィードからの **URL** 評価を使用して、既知の悪意のある URL を持つメッセージをブロックします。</span><span class="sxs-lookup"><span data-stu-id="bf44f-163">Microsoft uses a determination of reputation from URL sandboxing as well as URL reputation from third party feeds in **URL reputation blocking**, to block any message with a known malicious URL.</span></span>

8. <span data-ttu-id="bf44f-164">**コンテンツ ヒューリスティックは** 、機械学習モデルを使用して、メッセージの本文内の構造と単語の頻度に基づいて疑わしいメッセージを検出できます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-164">**Content heuristics** can detect suspicious messages based on structure and word frequency within the body of the message, using machine learning models.</span></span>

9. <span data-ttu-id="bf44f-165">**セーフ添付ファイルは**、動的分析を使用して、Office 365前に見えたことがない脅威を検出するために、Defender 用のすべての添付ファイルをサンドボックス化します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-165">**Safe Attachments** sandboxes every attachment for Defender for Office 365 customers, using dynamic analysis to detect never-before seen threats.</span></span>

10. <span data-ttu-id="bf44f-166">**リンクされたコンテンツの削除** は、メール内のファイルにリンクしているすべての URL を添付ファイルとして扱い、配信時にファイルを非同期的にサンドボックス化します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-166">**Linked content detonation** treats every URL linking to a file in an email as an attachment, asynchronously sandboxing the file at the time of delivery.</span></span>

11. <span data-ttu-id="bf44f-167">**URL の削除は** 、アップストリームのフィッシング対策テクノロジで疑わしいメッセージまたは URL が検出された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-167">**URL Detonation** happens when upstream anti-phishing technology finds a message or URL to be suspicious.</span></span> <span data-ttu-id="bf44f-168">URL のデトレーションサンドボックスは、配信時にメッセージ内の URL をサンドボックス化します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-168">URL detonation sandboxes the URLs in the message at the time of delivery.</span></span>

## <a name="phase-4---post-delivery-protection"></a><span data-ttu-id="bf44f-169">フェーズ 4 - 配信後の保護</span><span class="sxs-lookup"><span data-stu-id="bf44f-169">Phase 4 - Post-Delivery Protection</span></span>

<span data-ttu-id="bf44f-170">最後のステージは、メールまたはファイルの配信後に行い、さまざまなメールボックス内のメールや、Microsoft Teams のようなクライアントに表示されるファイルやリンクに基Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="bf44f-170">The last stage takes place after mail or file delivery, acting on mail that is in various mailboxes and files and links that appear in clients like Microsoft Teams.</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase4.png" alt-text="Defender for Office 365のフェーズ 4 は、配信後の保護です。":::

1. <span data-ttu-id="bf44f-172">**セーフリンクは**、MDO のクリック時保護です。</span><span class="sxs-lookup"><span data-stu-id="bf44f-172">**Safe Links** is MDO's time-of-click protection.</span></span> <span data-ttu-id="bf44f-173">すべてのメッセージのすべての URL は、Microsoft のリンク サーバーをポイントセーフされます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-173">Every URL in every message is wrapped to point to Microsoft Safe Links servers.</span></span> <span data-ttu-id="bf44f-174">URL をクリックすると、ユーザーがターゲット サイトにリダイレクトされる前に、最新の評価に対してチェックされます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-174">When a URL is clicked it is checked against the latest reputation, before the user is redirected to the target site.</span></span> <span data-ttu-id="bf44f-175">URL は、評判を更新するために非同期的にサンドボックス化されます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-175">The URL is asynchronously sandboxed to update its reputation.</span></span>

2. <span data-ttu-id="bf44f-176">**フィッシング Zero-Hour自動パージ (ZAP)** は、既にメールボックスに配信されている悪意のあるフィッシング メッセージをさかのぼって検出Exchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="bf44f-176">**Phish Zero-Hour Auto-purge (ZAP)** retroactively detects and neutralizes malicious phishing messages that have already been delivered to Exchange Online mailboxes.</span></span>

3. <span data-ttu-id="bf44f-177">**マルウェア ZAP は**、既にメールボックスに配信されている悪意のあるマルウェア メッセージをさかのぼって検出Exchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="bf44f-177">**Malware ZAP** retroactively detects and neutralizes malicious malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

4. <span data-ttu-id="bf44f-178">**Spam ZAP は**、既にメールボックスに配信されている悪意のあるスパム メッセージをさかのぼって検出Exchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="bf44f-178">**Spam ZAP** retroactively detects and neutralizes malicious spam messages that have already been delivered to Exchange Online mailboxes.</span></span>

5. <span data-ttu-id="bf44f-179">**キャンペーン ビューを** 使用すると、管理者は自動化を行わずに、どのチームよりも速く、より完全に攻撃の大きな画像を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-179">**Campaign Views** let administrators see the big picture of an attack, faster and more completely, than any team could without automation.</span></span> <span data-ttu-id="bf44f-180">Microsoft は、サービス全体で膨大な量のフィッシング対策、スパム対策、マルウェア対策データを活用してキャンペーンを特定し、管理者がターゲット、影響、フローなど、ダウンロード可能なキャンペーンの書き込みにも使用できるデータを最初から最後まで調査できます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-180">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns, and then allows admins to investigate them from start to end, including targets, impacts, and flows, that are also available in a downloadable campaign write-up.</span></span>

6. <span data-ttu-id="bf44f-181">**レポート メッセージ** アドインを使用すると、ユーザーは誤検知 (良い電子メール、誤って悪いと *マークされている)* または誤検知 (良いとマークされた悪い *メール)* を Microsoft に簡単に報告し、さらに分析できます。</span><span class="sxs-lookup"><span data-stu-id="bf44f-181">**The Report Message add-ins** enable people to easily report false positives (good email, mistakenly marked as *bad*) or false negatives (bad email marked as *good*) to Microsoft for further analysis.</span></span>

7. <span data-ttu-id="bf44f-182">**セーフ** Office クライアントのリンクは、Word、PowerPoint、および Excel のような Office クライアントの内部で、ネイティブで同じ セーフ リンクのクリック時保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-182">**Safe Links for Office clients** offers the same Safe Links time-of-click protection, natively, inside of Office clients like Word, PowerPoint, and Excel.</span></span>

8. <span data-ttu-id="bf44f-183">**OneDrive、SharePoint、および Teams** の保護は、OneDrive、SharePoint、および Microsoft Teams の内部で、ネイティブで、悪意のあるファイルに対して同じ セーフ 添付ファイル保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-183">**Protection for OneDrive, SharePoint, and Teams** offers the same Safe Attachments protection against malicious files, natively, inside of OneDrive, SharePoint, and Microsoft Teams.</span></span>

9. <span data-ttu-id="bf44f-184">ファイルをポイントする URL が配信後に選択されている場合、リンクされたコンテンツの削除は、ファイルのサンドボックスが完了し、URL が安全である場合まで警告ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-184">When a URL that points to a file is selected post delivery, **linked content detonation** displays a warning page until the sandboxing of the file is complete, and the URL is found to be safe.</span></span>


## <a name="the-filtering-stack-diagram"></a><span data-ttu-id="bf44f-185">フィルター スタックの図</span><span class="sxs-lookup"><span data-stu-id="bf44f-185">The filtering stack diagram</span></span>

<span data-ttu-id="bf44f-186">最終的な図 (構成するダイアグラムのすべての部分と同様) は、製品の成長と開発に応じて *変更される可能性があります*。</span><span class="sxs-lookup"><span data-stu-id="bf44f-186">The final diagram (as with all parts of the diagram composing it) *is subject to change as the product grows and develops*.</span></span> <span data-ttu-id="bf44f-187">このページをブックマーク **し、更新** 後に確認する必要がある場合は、下部にあるフィードバック オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-187">Bookmark this page and use the **feedback** option you'll find at the bottom if you need to ask after updates.</span></span> <span data-ttu-id="bf44f-188">レコードの場合、これはすべてのフェーズを順番に持つスタックです。</span><span class="sxs-lookup"><span data-stu-id="bf44f-188">For your records, this is the the stack with all the phases in order:</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase5.png" alt-text="MDO で 1 ~ 4 の順序でフィルター処理のすべてのフェーズ。":::

## <a name="more-information"></a><span data-ttu-id="bf44f-190">詳細情報</span><span class="sxs-lookup"><span data-stu-id="bf44f-190">More information</span></span>

<span data-ttu-id="bf44f-191">Microsoft Defender for Office 365 \* 今すぐ _を **設定する必要** がありますか?</span><span class="sxs-lookup"><span data-stu-id="bf44f-191">Do you need to set up Microsoft Defender for Office 365 \***right now** _?</span></span> <span data-ttu-id="bf44f-192">このスタック (_now\*) を使用して[](protect-against-threats.md)、組織の保護を開始します。</span><span class="sxs-lookup"><span data-stu-id="bf44f-192">Use this stack, _now\*, with [this step-by-step](protect-against-threats.md) to start protecting your organization.</span></span>

<span data-ttu-id="bf44f-193">*MSFTTracyP と* ドキュメント作成チームからこのコンテンツに対する Giulian Garruba への特別な感謝。</span><span class="sxs-lookup"><span data-stu-id="bf44f-193">*Special thanks from MSFTTracyP and the docs writing team to Giulian Garruba for this content*.</span></span>
