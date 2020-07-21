---
title: Microsoft セキュリティスコアの新機能
description: Microsoft 365 セキュリティセンターの Microsoft セキュリティスコアに対して発生した新しい変更点について説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュア スコア、セキュリティ センター、改善のための処置
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: 4f9f4f40b9cd88cad1676417d467d04367eaa0be
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200147"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="cf1b0-104">Microsoft セキュリティスコアの新機能</span><span class="sxs-lookup"><span data-stu-id="cf1b0-104">What's new in Microsoft Secure Score</span></span>

<span data-ttu-id="cf1b0-105">Microsoft のセキュリティの評価をより良いものにするには、いくつかの変更を行いました。</span><span class="sxs-lookup"><span data-stu-id="cf1b0-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="cf1b0-106">予定されている変更の詳細については、「 [Microsoft Secure Score の内容](microsoft-secure-score-whats-coming.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf1b0-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

## <a name="june-2020"></a><span data-ttu-id="cf1b0-107">2020 年 6 月</span><span class="sxs-lookup"><span data-stu-id="cf1b0-107">June 2020</span></span>

### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="cf1b0-108">Microsoft Defender Advanced Threat Protection の改善アクションを削除しました</span><span class="sxs-lookup"><span data-stu-id="cf1b0-108">Removed improvement action for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="cf1b0-109">Attack Surface Reduction ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="cf1b0-109">Turn on Attack Surface Reduction rules</span></span>

### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="cf1b0-110">Microsoft Defender Advanced Threat Protection の改善アクションが追加されました</span><span class="sxs-lookup"><span data-stu-id="cf1b0-110">Added improvement actions for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="cf1b0-111">Adobe Reader が子プロセスを作成するのをブロックする</span><span class="sxs-lookup"><span data-stu-id="cf1b0-111">Block Adobe Reader from creating child processes</span></span>
* <span data-ttu-id="cf1b0-112">ランサムウェアに対する高度な保護の使用</span><span class="sxs-lookup"><span data-stu-id="cf1b0-112">Use advanced protection against ransomware</span></span>
* <span data-ttu-id="cf1b0-113">すべての Office アプリケーションで子プロセスを作成することを禁止する</span><span class="sxs-lookup"><span data-stu-id="cf1b0-113">Block all Office applications from creating child processes</span></span>
* <span data-ttu-id="cf1b0-114">Office アプリケーションで実行可能なコンテンツを作成することを禁止する</span><span class="sxs-lookup"><span data-stu-id="cf1b0-114">Block Office applications from creating executable content</span></span>
* <span data-ttu-id="cf1b0-115">JavaScript または VBScript がダウンロードされた実行可能コンテンツを起動するのをブロックする</span><span class="sxs-lookup"><span data-stu-id="cf1b0-115">Block JavaScript or VBScript from launching downloaded executable content</span></span>
* <span data-ttu-id="cf1b0-116">難読化する可能性のあるスクリプトの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="cf1b0-116">Block execution of potentially obfuscated scripts</span></span>
* <span data-ttu-id="cf1b0-117">電子メールクライアントおよび webmail からの実行可能ファイルのコンテンツをブロックする</span><span class="sxs-lookup"><span data-stu-id="cf1b0-117">Block executable content from email client and webmail</span></span>
* <span data-ttu-id="cf1b0-118">Office コミュニケーションアプリケーションによる子プロセスの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="cf1b0-118">Block Office communication application from creating child processes</span></span>
* <span data-ttu-id="cf1b0-119">USB から実行される信頼できないおよび署名されていないプロセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="cf1b0-119">Block untrusted and unsigned processes that run from USB</span></span>
* <span data-ttu-id="cf1b0-120">WMI イベントサブスクリプション経由の永続化をブロックする</span><span class="sxs-lookup"><span data-stu-id="cf1b0-120">Block persistence through WMI event subscription</span></span>
* <span data-ttu-id="cf1b0-121">Office アプリケーションが他のプロセスにコードを挿入するのをブロックする</span><span class="sxs-lookup"><span data-stu-id="cf1b0-121">Block Office applications from injecting code into other processes</span></span>
* <span data-ttu-id="cf1b0-122">実行可能ファイルが、流行、年齢、または信頼できるリストの条件を満たしていない限り、実行を禁止する</span><span class="sxs-lookup"><span data-stu-id="cf1b0-122">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
* <span data-ttu-id="cf1b0-123">PSExec および WMI コマンドからのプロセス作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="cf1b0-123">Block process creations originating from PSExec and WMI commands</span></span>
* <span data-ttu-id="cf1b0-124">Windows ローカルセキュリティ機関サブシステムからの資格情報の盗用をブロックする (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="cf1b0-124">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
* <span data-ttu-id="cf1b0-125">Office マクロからの Win32 API 呼び出しをブロックする</span><span class="sxs-lookup"><span data-stu-id="cf1b0-125">Block Win32 API calls from Office macros</span></span>

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="cf1b0-126">Id のセキュリティで保護されたスコアとグラフ API の非互換性</span><span class="sxs-lookup"><span data-stu-id="cf1b0-126">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="cf1b0-127">Microsoft Secure Score の最近のリリースでは、向上したスコアリングモデルがリリースされました。</span><span class="sxs-lookup"><span data-stu-id="cf1b0-127">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="cf1b0-128">これらの変更により、より柔軟かつ正確にセキュリティ状況を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="cf1b0-128">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="cf1b0-129">しかし、これらの更新プログラムにより、Microsoft セキュリティスコアが Id のセキュリティで保護されたスコアと Graph API とは一時的に互換性がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="cf1b0-129">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="cf1b0-130">時間では、Id のセキュリティスコアと Graph API が新しいスコアリングモデルを採用します。</span><span class="sxs-lookup"><span data-stu-id="cf1b0-130">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="cf1b0-131">その後、Microsoft のセキュリティで保護されたスコア、Id のセキュリティで保護されたスコア、Graph API によって報告されたスコアの違いがわかります。</span><span class="sxs-lookup"><span data-stu-id="cf1b0-131">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="cf1b0-132">ご不便をかけて申し訳ございません。今後、このようなエクスペリエンスの互換性を確保するために取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="cf1b0-132">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="cf1b0-133">更新された改善アクション</span><span class="sxs-lookup"><span data-stu-id="cf1b0-133">Updated improvement actions</span></span>

- <span data-ttu-id="cf1b0-134">Azure Active Directory の改善アクションを追加しました</span><span class="sxs-lookup"><span data-stu-id="cf1b0-134">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="cf1b0-135">Azure Advanced Threat Protection の向上アクションを追加しました</span><span class="sxs-lookup"><span data-stu-id="cf1b0-135">Added Azure Advanced Threat Protection improvement actions</span></span>
- <span data-ttu-id="cf1b0-136">Microsoft Defender ATP の[脅威 & 脆弱性管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)のセキュリティに関する推奨事項のサポート</span><span class="sxs-lookup"><span data-stu-id="cf1b0-136">Support for Microsoft Defender ATP [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="cf1b0-137">リリースされた TVM で提供されるすべてのセキュリティの推奨事項を使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="cf1b0-137">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="cf1b0-138">更新されたインターフェイスと機能</span><span class="sxs-lookup"><span data-stu-id="cf1b0-138">Updated interface and functionality</span></span>

* <span data-ttu-id="cf1b0-139">CISO およびリード レベルのディスカッションのすべての新しい指標と傾向の表示</span><span class="sxs-lookup"><span data-stu-id="cf1b0-139">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="cf1b0-140">スコアを追跡して評価するための新しい方法</span><span class="sxs-lookup"><span data-stu-id="cf1b0-140">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="cf1b0-141">スコア回帰の追跡と理解の向上</span><span class="sxs-lookup"><span data-stu-id="cf1b0-141">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="cf1b0-142">改善のための処置のフィルタリング、タグ付け、検索、グループ化</span><span class="sxs-lookup"><span data-stu-id="cf1b0-142">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="cf1b0-143">スコア予測と計画されているアクションを使用して、将来の目標に向けて管理する</span><span class="sxs-lookup"><span data-stu-id="cf1b0-143">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="cf1b0-144">その他多数。</span><span class="sxs-lookup"><span data-stu-id="cf1b0-144">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="cf1b0-145">ご意見をお聞かせください。</span><span class="sxs-lookup"><span data-stu-id="cf1b0-145">We want to hear from you</span></span>

<span data-ttu-id="cf1b0-146">問題がある場合は、[Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティに投稿してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="cf1b0-146">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="cf1b0-147">コミュニティを監視しているので、問題に対応します。</span><span class="sxs-lookup"><span data-stu-id="cf1b0-147">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="cf1b0-148">関連リソース</span><span class="sxs-lookup"><span data-stu-id="cf1b0-148">Related resources</span></span>

- [<span data-ttu-id="cf1b0-149">セキュリティの姿勢を評価する</span><span class="sxs-lookup"><span data-stu-id="cf1b0-149">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="cf1b0-150">Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="cf1b0-150">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="cf1b0-151">今後の予定</span><span class="sxs-lookup"><span data-stu-id="cf1b0-151">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
