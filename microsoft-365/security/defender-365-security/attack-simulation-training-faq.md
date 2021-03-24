---
title: 攻撃シミュレーション トレーニングの展開に関する考慮事項と FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Microsoft 365 E5 または Microsoft Defender for Office 365 Plan 2 組織での攻撃シミュレーションとトレーニングに関する展開に関する考慮事項とよく寄せられる質問について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f404e2a47756a611135fc70026bf0cce3eec62c4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065531"
---
# <a name="attack-simulation-training-deployment-considerations-and-faq"></a><span data-ttu-id="58342-103">攻撃シミュレーション トレーニングの展開に関する考慮事項と FAQ</span><span class="sxs-lookup"><span data-stu-id="58342-103">Attack simulation training deployment considerations and FAQ</span></span>

<span data-ttu-id="58342-104">攻撃シミュレーションのトレーニングが [一般提供されました](https://techcommunity.microsoft.com/t5/microsoft-security-and/attack-simulation-training-in-microsoft-defender-for-office-365/ba-p/2037291)。</span><span class="sxs-lookup"><span data-stu-id="58342-104">Attack simulation training is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-security-and/attack-simulation-training-in-microsoft-defender-for-office-365/ba-p/2037291).</span></span> <span data-ttu-id="58342-105">攻撃シミュレーショントレーニングを使用すると、Microsoft 365 E5 または Microsoft Defender for Office 365 Plan 2 組織は、実際の、武器化されたフィッシング ペイロードを利用したフィッシング シミュレーションの作成と管理を可能にすることで、ソーシャル エンジニアリング リスクを測定および管理できます。</span><span class="sxs-lookup"><span data-stu-id="58342-105">Attack simulation training enables Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2 organizations to measure and manage social engineering risk by allowing the creation and management of phishing simulations that are powered by real-world, de-weaponized phishing payloads.</span></span> <span data-ttu-id="58342-106">テラノバ のセキュリティと提携して提供されるハイパーターゲットトレーニングは、知識の向上と従業員の行動の変更に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="58342-106">Hyper-targeted training, delivered in partnership with Terranova security, helps improve knowledge and change employee behavior.</span></span>

<span data-ttu-id="58342-107">攻撃シミュレーション トレーニングの開始方法の詳細については、「攻撃シミュレーション トレーニングの使用を開始する [」を参照してください](attack-simulation-training-get-started.md)。</span><span class="sxs-lookup"><span data-stu-id="58342-107">For more information about getting started with Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="58342-108">シミュレーションの作成とスケジューリングの全体のエクスペリエンスは、自由に流れ、摩擦のない状態で設計されているが、企業規模でシミュレーションを実行するには計画が必要な場合が多い。</span><span class="sxs-lookup"><span data-stu-id="58342-108">While the whole simulation creation and scheduling experience has been designed to be free-flowing and frictionless, running simulations at an enterprise scale often requires planning.</span></span> <span data-ttu-id="58342-109">この記事は、お客様が独自の環境でシミュレーションを実行する場合に見る特定の課題に対処するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="58342-109">This article helps address specific challenges that we see as our customers run simulations in their own environments.</span></span>

## <a name="issues-with-end-user-experiences"></a><span data-ttu-id="58342-110">エンド ユーザー エクスペリエンスに関する問題</span><span class="sxs-lookup"><span data-stu-id="58342-110">Issues with end user experiences</span></span>

### <a name="phishing-simulation-urls-blocked-by-google-safe-browsing"></a><span data-ttu-id="58342-111">Google セーフ ブラウズによってブロックされたフィッシング シミュレーション URL</span><span class="sxs-lookup"><span data-stu-id="58342-111">Phishing simulation URLs blocked by Google Safe Browsing</span></span>

<span data-ttu-id="58342-112">URL レピュテーション サービスは、攻撃シミュレーション トレーニングで使用される 1 つ以上の URL を安全でないと識別する場合があります。</span><span class="sxs-lookup"><span data-stu-id="58342-112">A URL reputation service might identify one or more of the URLs that are used by Attack simulation training as unsafe.</span></span> <span data-ttu-id="58342-113">Google Chrome の Google セーフ ブラウジングは、詐欺サイトの先行メッセージを使用して、シミュレートされたフィッシング URL の一部 **をブロック** します。</span><span class="sxs-lookup"><span data-stu-id="58342-113">Google Safe Browsing in Google Chrome blocks some of the simulated phishing URLs with a **Deceptive site ahead** message.</span></span> <span data-ttu-id="58342-114">多くの URL レピュテーション ベンダーと一緒にシミュレーション URL を常に許可しますが、必ずしも完全にカバーできるとは限らない。</span><span class="sxs-lookup"><span data-stu-id="58342-114">While we work with many URL reputation vendors to always allow our simulation URLs, we don't always have full coverage.</span></span>

![Google Chrome でのサイト先行警告の欺瞞](../../media/attack-sim-chrome-deceptive-site-message.png)

<span data-ttu-id="58342-116">この問題は Microsoft Edge には影響しない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="58342-116">Note that this issue does not affect Microsoft Edge.</span></span>

<span data-ttu-id="58342-117">計画フェーズの一環として、フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーの URL の可用性を確認してください。</span><span class="sxs-lookup"><span data-stu-id="58342-117">As part of the planning phase, be sure to check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="58342-118">Url が Google セーフ ブラウズによってブロックされている場合[](https://support.google.com/chrome/a/answer/7532419)は、Google からこのガイダンスに従って URL へのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="58342-118">If the URLs are blocked by Google Safe Browsing, [follow this guidance](https://support.google.com/chrome/a/answer/7532419) from Google to allow access to the URLs.</span></span>

<span data-ttu-id="58342-119">現在攻撃 [シミュレーション トレーニングで](attack-simulation-training-get-started.md) 使用されている URL の一覧については、「攻撃シミュレーション トレーニングの使用を開始する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58342-119">Refer to [Get started using Attack simulation training](attack-simulation-training-get-started.md) for the list of URLs that are currently used by Attack simulation training.</span></span>

### <a name="phishing-simulation-and-admin-urls-blocked-by-network-proxy-solutions-and-filter-drivers"></a><span data-ttu-id="58342-120">ネットワーク プロキシ ソリューションとフィルター ドライバーによってブロックされるフィッシング シミュレーションと管理 URL</span><span class="sxs-lookup"><span data-stu-id="58342-120">Phishing simulation and admin URLs blocked by network proxy solutions and filter drivers</span></span>

<span data-ttu-id="58342-121">フィッシング シミュレーション URL と管理 URL の両方が、中間セキュリティ デバイスまたはフィルターによってブロックまたは削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="58342-121">Both phishing simulation URLs and admin URLs might be blocked or dropped by your intermediate security devices or filters.</span></span> <span data-ttu-id="58342-122">例:</span><span class="sxs-lookup"><span data-stu-id="58342-122">For example:</span></span>

- <span data-ttu-id="58342-123">ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="58342-123">Firewalls</span></span>
- <span data-ttu-id="58342-124">Web アプリケーション ファイアウォール (WAF) ソリューション</span><span class="sxs-lookup"><span data-stu-id="58342-124">Web Application Firewall (WAF) solutions</span></span>
- <span data-ttu-id="58342-125">サード パーティ製フィルター ドライバー (カーネル モード フィルターなど)</span><span class="sxs-lookup"><span data-stu-id="58342-125">Third-party filter drivers (for example, kernel mode filters)</span></span>

<span data-ttu-id="58342-126">このレイヤーでブロックされているお客様は少ない一方で、発生します。</span><span class="sxs-lookup"><span data-stu-id="58342-126">While we have seen few customers being blocked at this layer, it does happen.</span></span> <span data-ttu-id="58342-127">問題が発生した場合は、必要に応じて、セキュリティ デバイスまたはフィルターによるスキャンをバイパスする次の URL を構成してください。</span><span class="sxs-lookup"><span data-stu-id="58342-127">If you encounter problems, consider configuring the following URLs to bypass scanning by your security devices or filters as required:</span></span>

- <span data-ttu-id="58342-128">「攻撃シミュレーション トレーニングの使用を開始する」の説明に従って、シミュレート [されたフィッシング URL を使用します](attack-simulation-training-get-started.md)。</span><span class="sxs-lookup"><span data-stu-id="58342-128">The simulated phishing URLs as described in [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
- <https://security.microsoft.com/attacksimulator>
- <https://security.microsoft.com/attacksimulationreport>
- <https://security.microsoft.com/trainingassignments>

### <a name="simulation-messages-not-delivered-to-all-targeted-users"></a><span data-ttu-id="58342-129">すべての対象ユーザーに配信されないシミュレーション メッセージ</span><span class="sxs-lookup"><span data-stu-id="58342-129">Simulation messages not delivered to all targeted users</span></span>

<span data-ttu-id="58342-130">シミュレーション電子メール メッセージを実際に受信するユーザーの数が、シミュレーションの対象となったユーザーの数よりも少ない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="58342-130">It's possible that the number of users who actually receive the simulation email messages is less than the number of users who were targeted by the simulation.</span></span> <span data-ttu-id="58342-131">次の種類のユーザーは、ターゲットの検証の一部として除外されます。</span><span class="sxs-lookup"><span data-stu-id="58342-131">The following types of users will be excluded as part of target validation:</span></span>

- <span data-ttu-id="58342-132">受信者の電子メール アドレスが無効です。</span><span class="sxs-lookup"><span data-stu-id="58342-132">Invalid recipient email addresses.</span></span>
- <span data-ttu-id="58342-133">ゲスト ユーザー。</span><span class="sxs-lookup"><span data-stu-id="58342-133">Guest users.</span></span>
- <span data-ttu-id="58342-134">Azure Active Directory (Azure Active Directory) でアクティブでなくなったAD。</span><span class="sxs-lookup"><span data-stu-id="58342-134">Users that are no longer active in Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="58342-135">有効なメールボックスを持つゲスト以外のユーザーだけがシミュレーションに含まれます。</span><span class="sxs-lookup"><span data-stu-id="58342-135">Only valid, non-guest users with a valid mailbox will be included in simulations.</span></span> <span data-ttu-id="58342-136">配布グループまたはメールが有効なセキュリティ グループを使用してユーザーをターゲットにする場合は[、Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)の[Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember)コマンドレットを使用して、配布グループのメンバーを表示および検証できます。</span><span class="sxs-lookup"><span data-stu-id="58342-136">If you use distribution groups or mail-enabled security groups to target users, you can use the [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember) cmdlet in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) to view and validate distribution group members.</span></span>

## <a name="issues-with-attack-simulation-training-reporting"></a><span data-ttu-id="58342-137">攻撃シミュレーショントレーニングレポートの問題</span><span class="sxs-lookup"><span data-stu-id="58342-137">Issues with Attack simulation training reporting</span></span>

### <a name="attack-simulation-training-reports-do-not-contain-any-activity-details"></a><span data-ttu-id="58342-138">攻撃シミュレーションのトレーニング レポートにアクティビティの詳細が含まれている</span><span class="sxs-lookup"><span data-stu-id="58342-138">Attack simulation training reports do not contain any activity details</span></span>

<span data-ttu-id="58342-139">攻撃シミュレーションのトレーニングには、豊富でアクション可能な分析情報が付属し、従業員の脅威の準備状況の進捗状況を知らせ続ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="58342-139">Attack simulation training comes with rich, actionable insights that keep you informed of the threat readiness progress of your employees.</span></span> <span data-ttu-id="58342-140">攻撃シミュレーション トレーニング レポートにデータが入力されていない場合は、組織内で監査ログ検索が有効になっていることを確認します (既定ではオンになっています)。</span><span class="sxs-lookup"><span data-stu-id="58342-140">If Attack simulation training reports are not populated with data, verify that audit log search is turned on in your organization (it's on by default).</span></span>

<span data-ttu-id="58342-141">監査ログの検索は、イベントをキャプチャ、記録、および読み取り戻しできるよう、攻撃シミュレーション トレーニングで必要です。</span><span class="sxs-lookup"><span data-stu-id="58342-141">Audit log search is required by Attack simulation training so events can be captured, recorded, and read back.</span></span> <span data-ttu-id="58342-142">監査ログ検索をオフにした場合、攻撃シミュレーション トレーニングでは次の結果が発生します。</span><span class="sxs-lookup"><span data-stu-id="58342-142">Turning off audit log search has the following consequences for Attack simulation training:</span></span>

- <span data-ttu-id="58342-143">レポート データは、すべてのレポートで使用できるとは言えな。</span><span class="sxs-lookup"><span data-stu-id="58342-143">Reporting data is not available across all reports.</span></span> <span data-ttu-id="58342-144">レポートは空に表示されます。</span><span class="sxs-lookup"><span data-stu-id="58342-144">The reports will appear empty.</span></span>
- <span data-ttu-id="58342-145">データを使用できないので、トレーニングの割り当てがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="58342-145">Training assignments are blocked, because data is not available.</span></span>

<span data-ttu-id="58342-146">監査ログ検索を有効にする方法については、「監査ログ検索 [を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="58342-146">To turn on audit log search, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

> [!NOTE]
> <span data-ttu-id="58342-147">空のアクティビティの詳細は、E5 ライセンスがユーザーに割り当てられていない場合にも発生します。</span><span class="sxs-lookup"><span data-stu-id="58342-147">Empty activity details can also be caused by no E5 licenses being assigned to users.</span></span> <span data-ttu-id="58342-148">少なくとも 1 つの E5 ライセンスがアクティブ ユーザーに割り当てられているのを確認して、レポート イベントがキャプチャおよび記録されます。</span><span class="sxs-lookup"><span data-stu-id="58342-148">Verify at least one E5 license is assigned to an active user to ensure that reporting events are captured and recorded.</span></span>

### <a name="simulation-reports-are-not-updated-immediately"></a><span data-ttu-id="58342-149">シミュレーション レポートが直ちに更新されない</span><span class="sxs-lookup"><span data-stu-id="58342-149">Simulation reports are not updated immediately</span></span>

<span data-ttu-id="58342-150">詳細なシミュレーション レポートは、キャンペーンを開始した直後には更新されません。</span><span class="sxs-lookup"><span data-stu-id="58342-150">Detailed simulation reports are not updated immediately after you launch a campaign.</span></span> <span data-ttu-id="58342-151">心配しないでください。この動作が予期されます。</span><span class="sxs-lookup"><span data-stu-id="58342-151">Don't worry; this behavior is expected.</span></span>

<span data-ttu-id="58342-152">すべてのシミュレーション キャンペーンにはライフサイクルがあります。</span><span class="sxs-lookup"><span data-stu-id="58342-152">Every simulation campaign has a lifecycle.</span></span> <span data-ttu-id="58342-153">最初に作成すると、シミュレーションはスケジュールされた **状態** になります。</span><span class="sxs-lookup"><span data-stu-id="58342-153">When first created, the simulation is in the **Scheduled** state.</span></span> <span data-ttu-id="58342-154">シミュレーションが開始されると、進行中の状態 **に移行** します。</span><span class="sxs-lookup"><span data-stu-id="58342-154">When the simulation starts, it transitions to the **In progress** state.</span></span> <span data-ttu-id="58342-155">完了すると、シミュレーションは完了状態 **に移行** します。</span><span class="sxs-lookup"><span data-stu-id="58342-155">When completed, the simulation transitions to the **Completed** state.</span></span>

<span data-ttu-id="58342-156">シミュレーションがスケジュールされた状態 **の間** 、シミュレーション レポートはほとんどの場合空になります。</span><span class="sxs-lookup"><span data-stu-id="58342-156">While a simulation is in the **Scheduled** state, the simulation reports will be mostly empty.</span></span> <span data-ttu-id="58342-157">この段階では、シミュレーション エンジンはターゲット ユーザーの電子メール アドレスを解決し、配布グループを展開し、リストからゲスト ユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="58342-157">During this stage, the simulation engine is resolving the target user email addresses, expanding distribution groups, removing guest users from the list, etc.:</span></span>

![スケジュールされた状態でのレポート](../../media/attack-sim-empty-reporting.png)

<span data-ttu-id="58342-159">シミュレーションが進行中のステージ **に入** った後、レポートにトリクルを開始する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="58342-159">Once the simulation enters the **In progress** stage, you will notice information starting to trickle into the reporting:</span></span>

![進行中の状態でのレポート](../../media/attack-sim-in-progress.png)

<span data-ttu-id="58342-161">個々のシミュレーション レポートが進行中の状態に移行した後に更新するには、最大 30 分 **かかる場合** があります。</span><span class="sxs-lookup"><span data-stu-id="58342-161">It can take up to 30 minutes for the individual simulation reports to update after the transition to the **In progress** state.</span></span> <span data-ttu-id="58342-162">シミュレーションが完了状態に達するまで、レポート データは引き続 **き作成** されます。</span><span class="sxs-lookup"><span data-stu-id="58342-162">The report data continues to build until the simulation reaches the **Completed** state.</span></span> <span data-ttu-id="58342-163">レポートの更新は、次の間隔で行われます。</span><span class="sxs-lookup"><span data-stu-id="58342-163">Reporting updates occur at the following intervals:</span></span>

- <span data-ttu-id="58342-164">最初の 60 分間は 10 分ごとに。</span><span class="sxs-lookup"><span data-stu-id="58342-164">Every 10 minutes for the first 60 minutes.</span></span>
- <span data-ttu-id="58342-165">60 分後から 2 日まで 15 分ごとに。</span><span class="sxs-lookup"><span data-stu-id="58342-165">Every 15 minutes after 60 minutes until 2 days.</span></span>
- <span data-ttu-id="58342-166">2 日後から 7 日まで 30 分ごとに。</span><span class="sxs-lookup"><span data-stu-id="58342-166">Every 30 minutes after 2 days until 7 days.</span></span>
- <span data-ttu-id="58342-167">7 日後に 60 分ごとに。</span><span class="sxs-lookup"><span data-stu-id="58342-167">Every 60 minutes after 7 days.</span></span>

<span data-ttu-id="58342-168">[概要] **ページのウィジェット** は、組織のシミュレーション ベースのセキュリティ体制の概要を時間の間に提供します。</span><span class="sxs-lookup"><span data-stu-id="58342-168">Widgets on the **Overview** page provide a quick snapshot of your organization's simulation-based security posture over time.</span></span> <span data-ttu-id="58342-169">これらのウィジェットは、全体的なセキュリティの姿勢と時間の長い旅を反映しますので、各シミュレーション キャンペーンの完了後に更新されます。</span><span class="sxs-lookup"><span data-stu-id="58342-169">Because these widgets reflect your overall security posture and journey over time, they're updated after each simulation campaign is completed.</span></span>

> [!NOTE]
> <span data-ttu-id="58342-170">さまざまなレポート ページの **[エクスポート]** オプションを使用して、データを抽出できます。</span><span class="sxs-lookup"><span data-stu-id="58342-170">You can use the **Export** option on the various reporting pages to extract data.</span></span>

### <a name="messages-reported-as-phishing-by-users-arent-appearing-in-simulation-reports"></a><span data-ttu-id="58342-171">ユーザーがフィッシングとして報告したメッセージがシミュレーション レポートに表示されない</span><span class="sxs-lookup"><span data-stu-id="58342-171">Messages reported as phishing by users aren't appearing in simulation reports</span></span>

<span data-ttu-id="58342-172">攻撃シミュレーター トレーニングのシミュレーション レポートでは、ユーザーのアクティビティに関する詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="58342-172">Simulation reports in Attack simulator training provide details on user activity.</span></span> <span data-ttu-id="58342-173">例:</span><span class="sxs-lookup"><span data-stu-id="58342-173">For example:</span></span>

- <span data-ttu-id="58342-174">メッセージ内のリンクをクリックしたユーザー。</span><span class="sxs-lookup"><span data-stu-id="58342-174">Users who clicked on the link in the message.</span></span>
- <span data-ttu-id="58342-175">資格情報を渡したユーザー。</span><span class="sxs-lookup"><span data-stu-id="58342-175">Users who gave up their credentials.</span></span>
- <span data-ttu-id="58342-176">メッセージをフィッシングとして報告したユーザー。</span><span class="sxs-lookup"><span data-stu-id="58342-176">Users who reported the message as phishing.</span></span>

<span data-ttu-id="58342-177">ユーザーがフィッシングとして報告したメッセージが攻撃シミュレーション シミュレーション レポートでキャプチャされない場合、報告されたメッセージの Microsoft への配信をブロックしている Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="58342-177">If messages that users reported as phishing aren't captured in Attack simulation training simulation reports, there might be an Exchange mail flow rule (also known as a transport rule) that's blocking the delivery of the reported messages to Microsoft.</span></span> <span data-ttu-id="58342-178">メール フロー ルールが次のメール アドレスへの配信をブロックしていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="58342-178">Verify that any mail flow rules aren't blocking delivery to the following email addresses:</span></span>

- <span data-ttu-id="58342-179">junk@office365.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="58342-179">junk@office365.microsoft.com</span></span>
- <span data-ttu-id="58342-180">abuse@messaging.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="58342-180">abuse@messaging.microsoft.com</span></span>
- <span data-ttu-id="58342-181">phish@office365.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="58342-181">phish@office365.microsoft.com</span></span>
- <span data-ttu-id="58342-182">junk@office365.microsoft.com \_</span><span class="sxs-lookup"><span data-stu-id="58342-182">not\_junk@office365.microsoft.com</span></span>

## <a name="other-frequently-asked-questions"></a><span data-ttu-id="58342-183">その他のよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="58342-183">Other frequently asked questions</span></span>

### <a name="q-what-is-the-recommended-method-to-target-users-for-simulation-campaigns"></a><span data-ttu-id="58342-184">Q: シミュレーション キャンペーンでユーザーをターゲットに設定する推奨方法は何ですか?</span><span class="sxs-lookup"><span data-stu-id="58342-184">Q: What is the recommended method to target users for simulation campaigns?</span></span>

<span data-ttu-id="58342-185">A: ターゲット ユーザーに使用できるオプションは複数あります。</span><span class="sxs-lookup"><span data-stu-id="58342-185">A: Several options are available to target users:</span></span>

- <span data-ttu-id="58342-186">すべてのユーザーを含める (現在、40,000 人未満のユーザーを持つ組織で利用可能)。</span><span class="sxs-lookup"><span data-stu-id="58342-186">Include all users (currently available to organizations with less than 40,000 users).</span></span>
- <span data-ttu-id="58342-187">特定のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="58342-187">Choose specific users.</span></span>
- <span data-ttu-id="58342-188">CSV ファイルからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="58342-188">Select users from a CSV file.</span></span>
- <span data-ttu-id="58342-189">Azure ADベースのターゲット設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="58342-189">Azure AD group-based targeting.</span></span>

<span data-ttu-id="58342-190">対象ユーザーが Azure グループによって識別されるキャンペーンは、通常、AD簡単に管理できると分かっています。</span><span class="sxs-lookup"><span data-stu-id="58342-190">We've found that campaigns where the targeted users are identified by Azure AD groups are generally easier to manage.</span></span>

### <a name="q-are-there-any-limits-in-targeting-users-while-importing-from-a-csv-or-adding-users"></a><span data-ttu-id="58342-191">Q: CSV からインポートする場合やユーザーを追加する場合、ユーザーのターゲット設定に制限はありますか?</span><span class="sxs-lookup"><span data-stu-id="58342-191">Q: Are there any limits in targeting users while importing from a CSV or adding users?</span></span>

<span data-ttu-id="58342-192">A: CSV ファイルから受信者をインポートするか、個々の受信者をシミュレーションに追加する制限は 40,000 です。</span><span class="sxs-lookup"><span data-stu-id="58342-192">A: The limit for importing recipients from a CSV file or adding individual recipients to a simulation is 40,000.</span></span>

<span data-ttu-id="58342-193">受信者には、個々のユーザーまたはグループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="58342-193">A recipient can be an individual user or a group.</span></span> <span data-ttu-id="58342-194">グループには数百人または数千人の受信者が含まれている可能性があります。したがって、実際の制限は個々のユーザーの数に設定されません。</span><span class="sxs-lookup"><span data-stu-id="58342-194">A group might contain hundreds or thousands of recipients, so an actual limit isn't placed on the number of individual users.</span></span>

<span data-ttu-id="58342-195">大きな CSV ファイルを管理したり、多数の個々の受信者を追加したりすると、面倒な場合があります。</span><span class="sxs-lookup"><span data-stu-id="58342-195">Managing a large CSV file or adding many individual recipients can be cumbersome.</span></span> <span data-ttu-id="58342-196">Azure ADグループを使用すると、シミュレーションの全体的な管理が簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="58342-196">Using Azure AD groups will simplify the overall management of the simulation.</span></span>

### <a name="q-does-microsoft-provide-payloads-in-other-languages"></a><span data-ttu-id="58342-197">Q: Microsoft は他の言語でペイロードを提供していますか?</span><span class="sxs-lookup"><span data-stu-id="58342-197">Q: Does Microsoft provide payloads in other languages?</span></span>

<span data-ttu-id="58342-198">A: 現在、5 つのローカライズされたペイロードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="58342-198">A: Currently, there are 5 localized payloads available.</span></span> <span data-ttu-id="58342-199">既存のペイロードを他の言語に直接翻訳したり機械翻訳したりすると、不正確で関連性が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="58342-199">We've noticed than any direct or machine translations of existing payloads to other languages will lead to inaccuracies and decreased relevance.</span></span>

<span data-ttu-id="58342-200">つまり、カスタム ペイロードの作成エクスペリエンスを使用して、選択した言語で独自のペイロードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="58342-200">That being said, you can create your own payload in the language of your choice using the custom payload authoring experience.</span></span> <span data-ttu-id="58342-201">また、特定の地域のユーザーをターゲットにするために使用された既存のペイロードを収集することを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="58342-201">We also strongly recommend that you harvest existing payloads that were used to target users in a specific geography.</span></span> <span data-ttu-id="58342-202">つまり、攻撃者がコンテンツをローカライズします。</span><span class="sxs-lookup"><span data-stu-id="58342-202">In other words, let the attackers localize the content for you.</span></span>

### <a name="q-how-can-i-switch-to-other-languages-for-my-admin-portal-and-training-experience"></a><span data-ttu-id="58342-203">Q: 管理ポータルとトレーニング エクスペリエンスのために他の言語に切り替える方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="58342-203">Q: How can I switch to other languages for my admin portal and training experience?</span></span>

<span data-ttu-id="58342-204">A: Microsoft 365 または Office 365 では、言語の構成はユーザー アカウントごとに固有で集中管理されています。</span><span class="sxs-lookup"><span data-stu-id="58342-204">A: In Microsoft 365 or Office 365, language configuration is specific and centralized for each user account.</span></span> <span data-ttu-id="58342-205">言語設定を変更する方法については [、「Microsoft 365 for Business](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b)の表示言語とタイム ゾーンを変更する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58342-205">For instructions on how to change your language setting, see [Change your display language and time zone in Microsoft 365 for Business](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b).</span></span>

<span data-ttu-id="58342-206">すべてのサービス間で同期するには、構成の変更に最大で 30 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="58342-206">Note that the configuration change might take up to 30 minutes to synchronize across all services.</span></span>

### <a name="q-can-i-trigger-a-test-simulation-to-understand-what-it-looks-like-prior-to-launching-a-full-fledged-campaign"></a><span data-ttu-id="58342-207">Q: 本格的なキャンペーンを開始する前に、テスト シミュレーションをトリガーして、その外観を把握できますか?</span><span class="sxs-lookup"><span data-stu-id="58342-207">Q: Can I trigger a test simulation to understand what it looks like prior to launching a full-fledged campaign?</span></span>

<span data-ttu-id="58342-208">A: はい、可能です。</span><span class="sxs-lookup"><span data-stu-id="58342-208">A: Yes you can!</span></span> <span data-ttu-id="58342-209">ウィザードの最後 **の [シミュレーションの** 確認] ページで、新しいシミュレーションを作成するには、テストを送信 **するオプションがあります**。</span><span class="sxs-lookup"><span data-stu-id="58342-209">On the very last **Review Simulation** page in the wizard to create a new simulation, there's an option to **Send a test**.</span></span> <span data-ttu-id="58342-210">このオプションは、現在ログインしているユーザーにフィッシング シミュレーション メッセージのサンプルを送信します。</span><span class="sxs-lookup"><span data-stu-id="58342-210">This option will send a sample phishing simulation message to the currently logged in user.</span></span> <span data-ttu-id="58342-211">受信トレイでフィッシング メッセージを検証した後、シミュレーションを送信できます。</span><span class="sxs-lookup"><span data-stu-id="58342-211">After you validate the phishing message in your Inbox, you can submit the simulation.</span></span>

![[シミュレーションの確認] ページの [テスト] ボタンを送信する](../../media/attack-sim-review-simulation-page.png)

### <a name="q-can-i-target-users-that-belong-to-a-different-tenant-as-part-of-the-same-simulation-campaign"></a><span data-ttu-id="58342-213">Q: 同じシミュレーション キャンペーンの一環として、別のテナントに属するユーザーをターゲットにできますか?</span><span class="sxs-lookup"><span data-stu-id="58342-213">Q: Can I target users that belong to a different tenant as part of the same simulation campaign?</span></span>

<span data-ttu-id="58342-214">A: いいえ。</span><span class="sxs-lookup"><span data-stu-id="58342-214">A: No.</span></span> <span data-ttu-id="58342-215">現在、テナント間シミュレーションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="58342-215">Currently, cross-tenant simulations are not supported.</span></span> <span data-ttu-id="58342-216">すべての対象ユーザーが同じテナントに入っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="58342-216">Verify that all of your targeted users are in the same tenant.</span></span> <span data-ttu-id="58342-217">テナント間のユーザーまたはゲスト ユーザーは、シミュレーション キャンペーンから除外されます。</span><span class="sxs-lookup"><span data-stu-id="58342-217">Any cross-tenant users or guest users will be excluded from the simulation campaign.</span></span>

### <a name="q-how-does-region-aware-delivery-work"></a><span data-ttu-id="58342-218">Q: 地域対応配信の動作について</span><span class="sxs-lookup"><span data-stu-id="58342-218">Q: How does region aware delivery work?</span></span>

<span data-ttu-id="58342-219">A: 地域対応配信では、対象ユーザーのメールボックスの TimeZone 属性を使用し、メッセージを配信する時期を決定するために "前に" ロジックを使用します。</span><span class="sxs-lookup"><span data-stu-id="58342-219">A: Region aware delivery uses the TimeZone attribute of the targeted user's mailbox and 'not before' logic to determine when to deliver the message.</span></span> <span data-ttu-id="58342-220">たとえば、次のシナリオを考えます。</span><span class="sxs-lookup"><span data-stu-id="58342-220">For example, consider the following scenario:</span></span>

- <span data-ttu-id="58342-221">太平洋タイム ゾーン (UTC-8) の午前 7 時に、管理者はキャンペーンを作成し、同じ日の午前 9 時に開始するスケジュールを設定します。</span><span class="sxs-lookup"><span data-stu-id="58342-221">At 7:00 AM in the Pacific time zone (UTC-8), an admin creates and schedules a campaign to start at 9:00 AM on the same day.</span></span>
- <span data-ttu-id="58342-222">UserA は東部タイム ゾーン (UTC-5) にあります。</span><span class="sxs-lookup"><span data-stu-id="58342-222">UserA is in the Eastern time zone (UTC-5).</span></span>
- <span data-ttu-id="58342-223">UserB は太平洋のタイム ゾーンにもいます。</span><span class="sxs-lookup"><span data-stu-id="58342-223">UserB is also in the Pacific time zone.</span></span>

<span data-ttu-id="58342-224">同じ日の午前 9 時に、シミュレーション メッセージが UserB に送信されます。</span><span class="sxs-lookup"><span data-stu-id="58342-224">At 9:00 AM on the same day, the simulation message is sent to UserB.</span></span> <span data-ttu-id="58342-225">地域対応の配信では、太平洋時間午前 9:00 は東部時間の午後 12:00 なので、メッセージは同じ日に UserA に送信されません。</span><span class="sxs-lookup"><span data-stu-id="58342-225">With region-aware delivery, the message is not sent to UserA on the same day, because 9:00 AM Pacific time is 12:00 PM Eastern time.</span></span> <span data-ttu-id="58342-226">代わりに、メッセージは、次の日の東部時間の午前 9:00 に UserA に送信されます。</span><span class="sxs-lookup"><span data-stu-id="58342-226">Instead, the message is sent to UserA at 9:00 AM Eastern time on the following day.</span></span>

<span data-ttu-id="58342-227">そのため、地域に対応した配信が有効になっているキャンペーンの最初の実行では、シミュレーション メッセージが特定のタイム ゾーンのユーザーにのみ送信された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="58342-227">So, on the initial run of a campaign with region aware delivery enabled, it might appear that the simulation message was sent only to users in a specific time zone.</span></span> <span data-ttu-id="58342-228">ただし、時間が経過し、スコープに入るユーザーが増えるほど、対象となるユーザーは増加します。</span><span class="sxs-lookup"><span data-stu-id="58342-228">But, as time passes and more users come into scope, the targeted users will increase.</span></span>