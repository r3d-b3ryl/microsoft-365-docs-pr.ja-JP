---
title: Microsoft Secure Score の新機能
description: Microsoft 365 セキュリティ センターの Microsoft Secure Score に加えた新しい変更について説明します。
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 1933ca86f56524b018c322f3b5560250debd0387
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064620"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="7d1af-104">Microsoft Secure Score の新機能</span><span class="sxs-lookup"><span data-stu-id="7d1af-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7d1af-105">Microsoft Secure Score をセキュリティの姿勢をより良くするために、いくつかの変更を加えた。</span><span class="sxs-lookup"><span data-stu-id="7d1af-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="7d1af-106">今後の変更については、「[Microsoft セキュア スコアの新機能](microsoft-secure-score-whats-coming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d1af-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)</span></span>

<span data-ttu-id="7d1af-107">Microsoft Secure Score は https://security.microsoft.com/securescore [、Microsoft 365](overview-security-center.md)セキュリティ センターにあります。</span><span class="sxs-lookup"><span data-stu-id="7d1af-107">Microsoft Secure Score can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>
    
## <a name="february-2021"></a><span data-ttu-id="7d1af-108">2021 年 2 月</span><span class="sxs-lookup"><span data-stu-id="7d1af-108">February 2021</span></span>

### <a name="compatibility-with-graph-api"></a><span data-ttu-id="7d1af-109">Graph API との互換性</span><span class="sxs-lookup"><span data-stu-id="7d1af-109">Compatibility with Graph API</span></span>

<span data-ttu-id="7d1af-110">Graph API を介して配信される Microsoft Secure Score の推奨事項は、Microsoft 365 セキュリティ センターに現在表示されている推奨事項と同じように表示され、重み付けされます。</span><span class="sxs-lookup"><span data-stu-id="7d1af-110">Microsoft Secure Score recommendations delivered via Graph API will look and be weighted the same as the recommendations you currently see in the Microsoft 365 security center.</span></span>

## <a name="january-2021"></a><span data-ttu-id="7d1af-111">2021 年 1 月</span><span class="sxs-lookup"><span data-stu-id="7d1af-111">January 2021</span></span>

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a><span data-ttu-id="7d1af-112">Microsoft Teams の最初のセキュリティ推奨事項を追加しました</span><span class="sxs-lookup"><span data-stu-id="7d1af-112">Added our first security recommendation for Microsoft Teams</span></span>

<span data-ttu-id="7d1af-113">Microsoft Teams のお客様は、Secure Score の新しい改善アクションとして「匿名ユーザーによる会議への参加を制限する」と表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d1af-113">Microsoft Teams customers will see "Restrict anonymous users from joining meetings" as a new improvement action in Secure Score.</span></span>

## <a name="december-2020"></a><span data-ttu-id="7d1af-114">2020年12月</span><span class="sxs-lookup"><span data-stu-id="7d1af-114">December 2020</span></span>

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="7d1af-115">Microsoft Defender for Endpoint (以前は Microsoft Defender ATP) に 6 つのアカウント関連の改善アクションを追加しました。</span><span class="sxs-lookup"><span data-stu-id="7d1af-115">Added six accounts-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="7d1af-116">'最小パスワード長' を '14 文字以上' に設定する</span><span class="sxs-lookup"><span data-stu-id="7d1af-116">Set 'Minimum password length' to '14 or more characters'</span></span>
- <span data-ttu-id="7d1af-117">[パスワード履歴の適用] を [24 以上のパスワード] に設定する</span><span class="sxs-lookup"><span data-stu-id="7d1af-117">Set 'Enforce password history' to '24 or more password(s)'</span></span>
- <span data-ttu-id="7d1af-118">[パスワードの最大保存期間] を [60 日以下] に設定しますが、0 には設定できません。</span><span class="sxs-lookup"><span data-stu-id="7d1af-118">Set 'Maximum password age' to '60 or fewer days, but not 0'</span></span>
- <span data-ttu-id="7d1af-119">[最小パスワードの使用時間] を [1 日以上] に設定する</span><span class="sxs-lookup"><span data-stu-id="7d1af-119">Set 'Minimum password age' to '1 or more day(s)'</span></span>
- <span data-ttu-id="7d1af-120">組み込みの管理者アカウントを無効にする</span><span class="sxs-lookup"><span data-stu-id="7d1af-120">Disable the built-in Administrator account</span></span>
- <span data-ttu-id="7d1af-121">組み込みのゲスト アカウントを無効にする</span><span class="sxs-lookup"><span data-stu-id="7d1af-121">Disable the built-in Guest account</span></span>

## <a name="november-2020"></a><span data-ttu-id="7d1af-122">2020 年 11 月</span><span class="sxs-lookup"><span data-stu-id="7d1af-122">November 2020</span></span>

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a><span data-ttu-id="7d1af-123">Secure Score を使用して ServiceNow チケットを作成する機能が削除されました</span><span class="sxs-lookup"><span data-stu-id="7d1af-123">Removed the ability to create ServiceNow tickets through Secure Score</span></span> 

<span data-ttu-id="7d1af-124">[ServiceNow の共有] にアクセスして Secure Score を使用して **ServiceNow チケット** >作成する機能は使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="7d1af-124">The ability to create ServiceNow tickets through Secure Score by going to **Share > ServiceNow** is no longer available.</span></span> <span data-ttu-id="7d1af-125">次の手順を決定する間、フィードバックと継続的なサポートに感謝します。</span><span class="sxs-lookup"><span data-stu-id="7d1af-125">Thank you for your feedback and continued support while we determine next steps.</span></span>

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="7d1af-126">Microsoft Defender for Endpoint (以前は Microsoft Defender ATP) に 3 つのサービス関連の改善アクションを追加しました。</span><span class="sxs-lookup"><span data-stu-id="7d1af-126">Added three services-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="7d1af-127">Windows サービスのクォートされていないサービス パスを修正する</span><span class="sxs-lookup"><span data-stu-id="7d1af-127">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="7d1af-128">サービスの実行可能パスを共通の保護された場所に変更する</span><span class="sxs-lookup"><span data-stu-id="7d1af-128">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="7d1af-129">Windows レジストリにキャッシュされたパスワードを回避するためにサービス アカウントを変更する</span><span class="sxs-lookup"><span data-stu-id="7d1af-129">Change service account to avoid cached password in windows registry</span></span>

## <a name="october-2020"></a><span data-ttu-id="7d1af-130">2020 年 10 月</span><span class="sxs-lookup"><span data-stu-id="7d1af-130">October 2020</span></span>

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="7d1af-131">Microsoft Defender for Endpoint に関連する改善アクションを削除する</span><span class="sxs-lookup"><span data-stu-id="7d1af-131">Remove improvement action related to Microsoft Defender for Endpoint</span></span>

- <span data-ttu-id="7d1af-132">Microsoft Defender SmartScreen Windows Store アプリの Web コンテンツ チェックを警告に設定する</span><span class="sxs-lookup"><span data-stu-id="7d1af-132">Set Microsoft Defender SmartScreen Windows Store app web content checking to warn</span></span>

## <a name="august-2020"></a><span data-ttu-id="7d1af-133">2020 年 8 月</span><span class="sxs-lookup"><span data-stu-id="7d1af-133">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="7d1af-134">Azure Active Directory の改善アクションを更新しました</span><span class="sxs-lookup"><span data-stu-id="7d1af-134">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="7d1af-135">レガシ認証をブロックするポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="7d1af-135">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score"></a><span data-ttu-id="7d1af-136">Identity Secure Score との非互換性</span><span class="sxs-lookup"><span data-stu-id="7d1af-136">Incompatibility with Identity Secure Score</span></span>

<span data-ttu-id="7d1af-137">Microsoft Secure Score の最近のリリースでは、スコアリング モデルが改善されました。</span><span class="sxs-lookup"><span data-stu-id="7d1af-137">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="7d1af-138">これらの変更により、セキュリティの態勢をより柔軟かつ正確に把握できます。</span><span class="sxs-lookup"><span data-stu-id="7d1af-138">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="7d1af-139">ただし、これらの更新プログラムにより、Microsoft Secure Score は一時的に Identity Secure Score と互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="7d1af-139">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score.</span></span>

<span data-ttu-id="7d1af-140">時間内に、Identity Secure Score は新しいスコアリング モデルを採用します。</span><span class="sxs-lookup"><span data-stu-id="7d1af-140">In time, Identity Secure Score will adopt the new scoring model.</span></span> <span data-ttu-id="7d1af-141">それまでは、Microsoft Secure Score と Identity Secure Score によって報告されたスコアの違いが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d1af-141">Until then, customers will see differences in the scores reported by Microsoft Secure Score and the Identity Secure Score.</span></span> <span data-ttu-id="7d1af-142">ご不便をおかけして申し訳ございませんが、今後、これらのエクスペリエンスの互換性を確保するために取り組み中です。</span><span class="sxs-lookup"><span data-stu-id="7d1af-142">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="7d1af-143">更新された改善アクション</span><span class="sxs-lookup"><span data-stu-id="7d1af-143">Updated improvement actions</span></span>

- <span data-ttu-id="7d1af-144">Azure Active Directory の改善アクションを追加しました</span><span class="sxs-lookup"><span data-stu-id="7d1af-144">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="7d1af-145">Microsoft Defender for Identity の改善アクションを追加しました</span><span class="sxs-lookup"><span data-stu-id="7d1af-145">Added Microsoft Defender for Identity improvement actions</span></span>
- <span data-ttu-id="7d1af-146">Microsoft Defender for Endpoint [Threat &のセキュリティ](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 推奨事項のサポート</span><span class="sxs-lookup"><span data-stu-id="7d1af-146">Support for Microsoft Defender for Endpoint [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="7d1af-147">TVM によって提供されるリリース済みセキュリティ推奨事項が利用可能にな</span><span class="sxs-lookup"><span data-stu-id="7d1af-147">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="7d1af-148">インターフェイスと機能の更新</span><span class="sxs-lookup"><span data-stu-id="7d1af-148">Updated interface and functionality</span></span>

* <span data-ttu-id="7d1af-149">CISO およびリード レベルのディスカッションのすべての新しい指標と傾向の表示</span><span class="sxs-lookup"><span data-stu-id="7d1af-149">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="7d1af-150">スコアを追跡して評価するための新しい方法</span><span class="sxs-lookup"><span data-stu-id="7d1af-150">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="7d1af-151">スコア回帰の追跡と理解の向上</span><span class="sxs-lookup"><span data-stu-id="7d1af-151">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="7d1af-152">改善のための処置のフィルタリング、タグ付け、検索、グループ化</span><span class="sxs-lookup"><span data-stu-id="7d1af-152">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="7d1af-153">スコア予測と計画されているアクションを使用して、将来の目標に向けて管理する</span><span class="sxs-lookup"><span data-stu-id="7d1af-153">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="7d1af-154">その他多数。</span><span class="sxs-lookup"><span data-stu-id="7d1af-154">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="7d1af-155">ご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="7d1af-155">We want to hear from you</span></span>

<span data-ttu-id="7d1af-156">問題がある場合は、セキュリティ、プライバシー、コンプライアンス コミュニティに投稿して [&してください](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 。</span><span class="sxs-lookup"><span data-stu-id="7d1af-156">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="7d1af-157">コミュニティを監視しているので、問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="7d1af-157">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="7d1af-158">関連リソース</span><span class="sxs-lookup"><span data-stu-id="7d1af-158">Related resources</span></span>

- [<span data-ttu-id="7d1af-159">セキュリティ体制にアクセス</span><span class="sxs-lookup"><span data-stu-id="7d1af-159">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="7d1af-160">Microsoft Secure Score の履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="7d1af-160">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="7d1af-161">今後の予定</span><span class="sxs-lookup"><span data-stu-id="7d1af-161">What's coming</span></span>](microsoft-secure-score-whats-coming.md)